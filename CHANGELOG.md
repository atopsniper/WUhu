# Changelog

## [2026-04-30] - Optimization & Formatting

### Code Quality
- Formatted `_worker.js` using Prettier with tab indentation.
- Added comments for Chinese variable names (核心配置变量, 缓存与调试标志, SOCKS5白名单).
- Enhanced `log` function to include ISO timestamp for better debugging.

### Configuration
- Added `.prettierrc` for consistent code formatting.
- Added GitHub Actions workflow `.github/workflows/lint.yml` to enforce formatting on push/pull_request.

### Security & Debugging
- Default `调试日志打印` remains disabled unless `DEBUG` environment variable is set to `1` or `true`.
- Log output now includes timestamp.

## [2026-04-30] - Initial Upgrade (Incomplete)

- Previously attempted upgrade with formatting and CI, but only documentation was updated.
- This release completes the actual code optimizations.
