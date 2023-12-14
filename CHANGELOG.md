## [1.1.0] - 2023-12-14

### Bug Fixes

- Clippy warnings

### Miscellaneous Tasks

- Add cliff.toml and release.toml
- Update release.toml
- Add release workflow
- Release uds_windows version 1.1.0

### Other

- Do the easy fixups; leave nullptr and saftey comment lints for another time

- Support I/O Safety types and traits: AsSocket, BorrowedSocket, OwnedSocket

This allows callers of uds_windows to potentially avoid having to use
the Raw types and traits.

This also allows the use of uds_windows with upcoming changes to
async-io to use AsFd.

Get compiling from old PR; add AsSocket for UnixStream

Cargo format

- Added safety comments above unsafe blocks within safe functions


## [1.0.2] - 2022-05-20

### Miscellaneous Tasks

- Add dependabot

### Other

- Replace deprecated tempdir with tempfile

- Create rust-clippy.yml

## [1.0.1] - 2021-02-03

### Other

- Don't use `mem::uninitialized()`

Follow the upstream `library/std/src/sys/unix/ext/net/addr.rs` approach.


## [1.0.0] - 2021-02-03

### Other

- Exclude `.github` from being packaged

## [0.1.6] - 2021-02-03

### Other

- Create Dependabot config file
- Update winapi


## [0.1.5] - 2020-07-03

### Other

- Add .idea to .gitignore

- Create rust.yml
- Cargo fmt

- Run on windows
- Remove warnings, and remove deny(warnings)

warnings appear in newer rustc versions, and we don't want to fail
because of these

- Version 0.1.5


## [0.1.4] - 2019-07-08

### Other

- V0.1.0

- Remove extra indirection from cast (#2)

The cast from `mio::Poll` and `mio::windows::Binding` to local copies (see issue #1 for more details) had a bug--an extra `&`. Somehow it was working in debug, but in release the code panicked with "0xC000001D: Illegal Instruction. occurred".

I replaced transmute with a regular cast (transmute was unnecessary), removed the extra indirection, changed the as_* functions to impls of AsRef, and added tests.
- Strip the mio part

- Corrected repo and README.md

- Add package.metadata.docs.rs
- Add UnixStream::pair()

- Cargo fmt

- Add socket timeout options

- Use AtomicUsize::new(0) instead of ATOMIC_USIZE_INIT

- Inc version


