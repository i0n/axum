# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

# Unreleased

- None.

# 0.3.0 (25. November, 2022)

- **added:** Add `#[derive(FromRequestParts)]` for deriving an implementation of
  `FromRequestParts`, similarly to `#[derive(FromRequest)]` ([#1305])
- **added:** Add `#[derive(FromRef)]` ([#1430])
- **added:** Add `#[from_ref(skip)]` to skip implementing `FromRef` for individual fields ([#1537])
- **added:** Support using a different rejection for `#[derive(FromRequest)]`
  with `#[from_request(rejection(MyRejection))]` ([#1256])
- **change:** axum-macro's MSRV is now 1.60 ([#1239])
- **breaking:** `#[derive(FromRequest)]` will no longer generate a rejection
  enum but instead generate `type Rejection = axum::response::Response`. Use the
  new `#[from_request(rejection(MyRejection))]` attribute to change this.
  The `rejection_derive` attribute has also been removed ([#1272])

[#1239]: https://github.com/tokio-rs/axum/pull/1239
[#1256]: https://github.com/tokio-rs/axum/pull/1256
[#1272]: https://github.com/tokio-rs/axum/pull/1272
[#1305]: https://github.com/tokio-rs/axum/pull/1305
[#1430]: https://github.com/tokio-rs/axum/pull/1430
[#1537]: https://github.com/tokio-rs/axum/pull/1537

<details>
<summary>0.3.0 Pre-Releases</summary>

# 0.3.0-rc.3 (18. November, 2022)

- **added:** Add `#[from_ref(skip)]` to skip implementing `FromRef` for individual fields ([#1537])

[#1537]: https://github.com/tokio-rs/axum/pull/1537

# 0.3.0-rc.2 (8. November, 2022)

- **added:** Add `#[derive(FromRef)]` ([#1430])

[#1430]: https://github.com/tokio-rs/axum/pull/1430

# 0.3.0-rc.1 (23. August, 2022)

- **change:** axum-macro's MSRV is now 1.60 ([#1239])
- **added:** Support using a different rejection for `#[derive(FromRequest)]`
  with `#[from_request(rejection(MyRejection))]` ([#1256])
- **breaking:** `#[derive(FromRequest)]` will no longer generate a rejection
  enum but instead generate `type Rejection = axum::response::Response`. Use the
  new `#[from_request(rejection(MyRejection))]` attribute to change this.
  The `rejection_derive` attribute has also been removed ([#1272])
- **added:** Add `#[derive(FromRequestParts)]` for deriving an implementation of
  `FromRequestParts`, similarly to `#[derive(FromRequest)]` ([#1305])

[#1239]: https://github.com/tokio-rs/axum/pull/1239
[#1256]: https://github.com/tokio-rs/axum/pull/1256
[#1272]: https://github.com/tokio-rs/axum/pull/1272
[#1305]: https://github.com/tokio-rs/axum/pull/1305

</details>

# 0.2.3 (27. June, 2022)

- **change:** axum-macros's MSRV is now 1.56 ([#1098])
- **fixed:** Silence "unnecessary use of `to_string`" lint for `#[derive(TypedPath)]` ([#1117])

[#1098]: https://github.com/tokio-rs/axum/pull/1098
[#1117]: https://github.com/tokio-rs/axum/pull/1117

# 0.2.2 (18. May, 2022)

- **added:** In `debug_handler`, check if `Request` is used as non-final extractor ([#1035])
- **added:** In `debug_handler`, check if multiple `Path` extractors are used ([#1035])
- **added:** In `debug_handler`, check if multiple body extractors are used ([#1036])
- **added:** Support customizing rejections for `#[derive(TypedPath)]` ([#1012])

[#1035]: https://github.com/tokio-rs/axum/pull/1035
[#1036]: https://github.com/tokio-rs/axum/pull/1036
[#1012]: https://github.com/tokio-rs/axum/pull/1012

# 0.2.1 (10. May, 2022)

- **fixed:** `Option` and `Result` are now supported in typed path route handler parameters ([#1001])
- **fixed:** Support wildcards in typed paths ([#1003])
- **added:** Support `#[derive(FromRequest)]` on enums using `#[from_request(via(OtherExtractor))]` ([#1009])
- **added:** Support using a custom rejection type for `#[derive(TypedPath)]`
  instead of `PathRejection` ([#1012])

[#1001]: https://github.com/tokio-rs/axum/pull/1001
[#1003]: https://github.com/tokio-rs/axum/pull/1003
[#1009]: https://github.com/tokio-rs/axum/pull/1009
[#1012]: https://github.com/tokio-rs/axum/pull/1012

# 0.2.0 (31. March, 2022)

- **breaking:** Routes are now required to start with `/`. Previously empty routes or routes such
  as `:foo` would be accepted but most likely result in bugs ([#823])

[#823]: https://github.com/tokio-rs/axum/pull/823

# 0.1.2 (1. March 2022)

- **fixed:** Use fully qualified `Result` type ([#796])

[#796]: https://github.com/tokio-rs/axum/pull/796

# 0.1.1 (22. February 2022)

- Add `#[derive(TypedPath)]` for use with axum-extra's new "type safe" routing API ([#756])

[#756]: https://github.com/tokio-rs/axum/pull/756

# 0.1.0 (31. January, 2022)

- Initial release.
