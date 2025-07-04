abi.encodePacked() Used with Dynamic Types — Risk of Ambiguous Output
abi.encodePacked() is used in string construction with dynamic and variable-length types (e.g., strings, integers converted to strings) without length-prefixing or clear delimiters. While currently used to construct a display string, this pattern becomes dangerous when reused in hash-based logic or signature generation, as it may result in ambiguous or colliding byte outputs.

Solidity’s packed encoding is non-injective for dynamic types — meaning two different sets of input can produce the same packed result. This becomes critical when such packed values are passed to keccak256() or used in verification mechanisms.

✅ Use abi.encode() for hashing and signatures.

✅ Use abi.encode() when dynamic types (like strings) are involved.

✅ Use abi.encodePacked() only with fixed types (e.g. uint256, address) if you're optimizing for gas or building plain strings.

❌ Never use abi.encodePacked() + keccak256() with multiple dynamic inputs.

Impact:

Ambiguity in data representation: Misleading or overlapping output when similar-looking inputs produce identical strings.

Future vulnerability vector: If the output is later passed to keccak256() or used in a signed message, it may introduce hash collision risks or allow signature reuse on different orders.

