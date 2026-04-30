
---
## 🔧 优化与升级 (2026-04-30)

- **代码格式化**：使用 `prettier` 对 JavaScript 代码进行统一格式化，消除多余空格和不一致的缩进。
- **中文变量统一**：在核心脚本中对中文变量名添加注释，以提升可读性并兼容 IDE 高亮。
- **安全增强**：默认关闭 `DEBUG`，并在日志前添加时间戳，避免泄露敏感信息。
- **文档升级**：在 `README.md` 增加 **部署全流程**、**变量说明**、**常见错误排查** 小节，帮助新手快速上手。
- **CI 支持**：新增 `.github/workflows/lint.yml`，在每次 push 时自动运行 `prettier` 检查。

### 📦 新增文件
- `CHANGELOG.md` – 记录每次发布的改动。
- `.prettierrc` – Prettier 配置文件。
- `.github/workflows/lint.yml` – GitHub Actions 自动检查代码风格。

### 🚀 部署建议（避免被 Cloudflare 屏蔽）
1. **使用自定义域**：在 Workers 控制台绑定已备案的子域，避免使用 `*.workers.dev` 直接公开。
2. **开启 Bot Protection**：在 Cloudflare Dashboard → **Bots** 页面打开 **Bot Fight Mode**，可减轻自动化请求被拦截的概率。
3. **设置安全头**：在 `wrangler.toml` 中加入 `[[routes]]` 并配置 `security_headers`，如 `Content-Security-Policy`、`X-Content-Type-Options` 等。
4. **限制请求频率**：在 Workers 脚本里添加 IP 限流（`cf.throttle`）防止短时间大量请求触发 Cloudflare 防护。

详细的部署步骤请参考本仓库的 **《部署全流程》** 小节，或直接访问项目演示站点：<https://EDT-Pages.github.io/admin>。

---
