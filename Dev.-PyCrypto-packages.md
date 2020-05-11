### In shorts to understand PyCrypto packages differences

There are three library versions:
- PyCrypto (the original - not support all Python 3.x versions)
- PyCryptodome (fork of PyCrypto with many enhancements)
- PyCryptodomex (fork of PyCrypto with many enhancements)

### Which one to install depends on the needs

If you have installed PyCrypto will be installed on `Crypto` package folder.

If you install PyCryptodome over PyCrypto will be installed always on same `Crypto` package folder, but this could cause other applications to stop working, if they not support PyCryptodome.

If you install PyCryptodomex will be installed on `Cryptodome` package folder, then PyCrypto and PyCryptodomex can coexist.

### Python imports

The imports depends on the package:
- PyCrypto: Crypto
- PyCryptodome: Crypto
- PyCryptodomex: Cryptodome

Netflix add-on support all library packages.
