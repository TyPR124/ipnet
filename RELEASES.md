# Releases

## Version 2.0.0 (2018-08-21)

* The `Emu128` module has been removed. This provided an emulated 128-bit integer for supporting IPv6 addresses. As of Rust 1.26 the built-in 128-bit integers have been marked stable and this library has been updated to use these instead of `Emu128`.

* The `with-serde` feature name shim has been removed. The `serde` feature should now be used using the bare `serde` feature name per the Rust API Guidelines.

* The `Deref` on `Ipv4Net` and `Ipv6Net` has been removed. This dereferenced to the `Ipv4Addr` and `Ipv6Addr` contained in the type. To use these methods call them directly on the contained IP address of interest, which may be accessed using the `addr()` or `network()` methods.

* In prior versions it was necessary to use the `Contains` trait to access the `contains()` methods. These are now inherited in public methods on the `IpNet`, `Ipv4Net`, and `Ipv6Net` types so are always available.

* The implementations of `IpAdd<u32>` and `IpSub<u32>` for IpAddr have been removed.

* The implementations of `IpAdd<u32>` and `IpSub<u32>` for `Ipv6Addr` have been removed.

## Version 1.2.1 (2018-06-06)

* Fix to resolve an issue with the optional serde support, where compact binary formats were not properly supported. See issue #10.

## Version 1.2.0 (2018-04-17)

* The previous release (1.1.0) introduced serde support using the feature name `with-serde`, but the Rust API Guidelines recommend using `serde` as the name of the feature. This release changes the feature name from `with-serde` to `serde`, but it is backwards compatible for those that already started using the `with-serde` feature name. The 1.1.0 release was yanked on crates.io to discourage further use of this feature name. See pull request #7.

## Version 1.1.0 (2018-04-13)

* Adds serde support. See pull request #6.
