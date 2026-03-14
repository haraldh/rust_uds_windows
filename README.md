# uds_windows

Forked from https://github.com/Azure/mio-uds-windows.

A library for integrating Unix domain sockets on Windows. Similar to the
standard library's [support for Unix sockets][std].

## Structure

Most of the exported types in `uds_windows` are analagous to the Unix-specific
types in [std], but have been adapted for Windows.

Two "extension" traits, `UnixListenerExt` and `UnixStreamExt`, and their
implementations, were adapted from their TCP counterparts in the [miow] library.

## Windows support for Unix domain sockets

Support for Unix domain sockets was introduced in Windows 10
[Insider Build 17063][af-unix-preview]. It became generally available in version
1809 (aka the October 2018 Update), and in Windows Server 1809/2019.

[af-unix-preview]: https://devblogs.microsoft.com/commandline/af_unix-comes-to-windows/
[miow]: https://github.com/yoshuawuyts/miow
[std]: https://doc.rust-lang.org/std/os/unix/net/

## License

This project is licensed under MIT license ([LICENSE](LICENSE) or
https://opensource.org/license/mit).
