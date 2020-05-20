# ENS Namehash

This package is a fork of the Consensys implementation of the *namehash* algorithm from
[EIP137](https://github.com/ethereum/EIPs/issues/137).

It was written to use the `pysha3` module for the non-standardized version of SHA3, referred to as `keccak256()` in Solidity usually.

But looks like the `pysha3` implementation does not carry the version of SHA3 that can be substituted for Keccak. This fork substitutes that with the `keccak()` supplied by the `eth-utils` library.

### Quickstart

Install the package:

```bash
$ pip install ens-namehash
```

Hash some names!


```python
>>> from namehash import namehash
>>> namehash('')
... b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
>>> namehash('eth')
... b'\x93\xcd\xebp\x8buE\xdcf\x8e\xb9(\x01v\x16\x9d\x1c3\xcf\xd8\xedo\x04i\n\x0b\xcc\x88\xa9?\xc4\xae'
>>> namehash('foo.eth')
... b'\xde\x9b\t\xfd|_\x90\x1e#\xa3\xf1\x9f\xec\xc5H(\xe9\xc8HS\x98\x01\xe8e\x91\xbd\x98\x01\xb0\x19\xf8O'
```
