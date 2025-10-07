# GameHub Lite

Open source privacy-respecting infrastructure for the GameHub Android app.

---

## 👋 About This Organization

GameHub Lite maintains open source alternatives to the proprietary GameHub app infrastructure. Our goal is to provide **privacy-respecting, transparent, and self-hostable** solutions for running GameHub without invasive tracking or data collection.

---

## 🚀 Projects

### [gamehub-worker](https://github.com/gamehublite/gamehub-worker)
**Cloudflare Worker-based API proxy**

Privacy-respecting API proxy that routes GameHub app requests to GitHub static files and sanitizes sensitive data when proxying to external servers.

**Features:**
- Hides user IP addresses from external servers
- Sanitizes device fingerprints (GPU configs only send vendor, not full device info)
- Routes static data through GitHub (transparent, auditable)
- Self-hostable (deploy to your own Cloudflare account)
- Zero runtime dependencies
- Free to run (Cloudflare free tier: 100k requests/day)

**Deployed Instance:** `https://gamehub-api.secureflex.workers.dev`

---

### [gamehub_api](https://github.com/gamehublite/gamehub_api)
**Static JSON API repository**

Hosts all configuration files, component manifests, and mock responses that were previously served by proprietary servers.

**Contents:**
- Component manifests (Box64, GPU drivers, DXVK, VKD3D, game profiles, libraries, Steam integration)
- App configuration files
- Steam CDN optimization data
- Empty responses for removed tracking features

**Access:** `https://raw.githubusercontent.com/gamehublite/gamehub_api/main/`

---

### [gamehub-oss](https://github.com/gamehublite/gamehub-oss)
**Security analysis and documentation**

Comprehensive security analysis, reverse engineering documentation, and technical reports for the GameHub APK modifications.

**Contents:**
- Comprehensive security analysis report (permission removal, authentication bypass, tracking removal)
- Bloat removal analysis (115MB → 55MB optimization breakdown)
- API architecture documentation
- Replication procedures and technical guides
- Modified APK (coming soon)

**Documentation:** Complete analysis of all privacy and security modifications

---

## 🔒 Privacy Philosophy

**What We Believe:**
- Users should control their own infrastructure
- Tracking and telemetry should be opt-in, not mandatory
- All code should be open source and auditable
- Privacy should be the default, not an afterthought

**What We Do:**
- ✅ Hide user IP addresses from external servers
- ✅ Sanitize device fingerprints before proxying
- ✅ Provide direct CDN download links (no proxy logging)
- ✅ Use GitHub for static data (transparent and auditable)
- ✅ Make everything self-hostable
- ✅ Zero proprietary dependencies

**What We Don't Do:**
- ❌ Log user behavior
- ❌ Collect device fingerprints
- ❌ Track locations
- ❌ Store personal data
- ❌ Inject analytics or telemetry

---

## 🛠️ Architecture

```
[GameHub App]
     ↓
[Cloudflare Worker] ← gamehub-worker (routes requests)
     ↓
     ├─→ GitHub ← gamehub_api (static data: manifests, configs)
     ├─→ External Servers (game metadata, GPU configs) [User IP hidden]
     └─→ Returns direct CDN links (downloads bypass proxy)
```

**Key Design Decisions:**
1. **Static data on GitHub** - Transparent, version-controlled, auditable
2. **Cloudflare Workers proxy** - Edge computing, fast worldwide, free tier
3. **No download proxying** - App downloads directly from CDN (no logging)
4. **Self-hostable** - Deploy to your own accounts in under 5 minutes

---

## 📦 Self-Hosting

**Want 100% control? Host everything yourself!**

All GameHub Lite projects are designed to be self-hosted. You can deploy to your own infrastructure and never trust third-party servers.

### Quick Start

**1. Deploy the Cloudflare Worker:**
```bash
git clone https://github.com/gamehublite/gamehub-worker.git
cd gamehub-worker
npm install
npm run deploy
# Output: https://gamehub-worker-YOUR-NAME.workers.dev
```

**2. Fork the static API repository:**
```bash
# Fork gamehub_api on GitHub
# Your URL: https://raw.githubusercontent.com/YOUR-USERNAME/gamehub_api/main/
```

**3. Update your APK:**
- Modify `EggGameHttpConfig.smali` to point to your worker URL
- Recompile and sign the APK
- You now control the entire stack!

**Total cost:** $0 (free tiers)

---

## 🎯 Use Cases

**For Privacy Enthusiasts:**
- Run GameHub without sending data to proprietary servers
- Self-host all infrastructure
- Audit all code yourself

**For Security Researchers:**
- Study Android reverse engineering techniques
- Learn about API proxying and privacy protection
- Understand telemetry removal methods

**For Developers:**
- Fork and modify for your own apps
- Learn Cloudflare Workers development
- Study privacy-preserving architectures

---

## 📚 Documentation

Each repository has comprehensive documentation:

- **gamehub-worker:** API endpoints, privacy features, deployment guide
- **gamehub_api:** Manifest formats, configuration files, maintenance procedures
- **gamehub-oss:** Complete security analysis, replication procedures, technical reports

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

**Code Contributions:**
- Improve the Cloudflare Worker code
- Add new component manifests
- Optimize performance
- Fix bugs

**Documentation:**
- Improve installation guides
- Add usage examples
- Translate documentation
- Create tutorials

**Testing:**
- Report issues
- Test self-hosting procedures
- Verify privacy features

**Please Note:** This project is for educational and research purposes. All contributions should respect applicable laws and ethical guidelines.

---

## ⚠️ Disclaimer

**Educational and Research Purposes Only**

This organization provides open source infrastructure for privacy research and education. Users are responsible for:
- Complying with all applicable laws
- Respecting software licenses and terms of service
- Using the code ethically and responsibly

We do not encourage or condone:
- Copyright infringement
- Terms of service violations
- Unauthorized access to systems
- Malicious use of the code

---

## 🔗 Links

- **Organization:** [github.com/gamehublite](https://github.com/gamehublite)
- **gamehub-worker repository:** [github.com/gamehublite/gamehub-worker](https://github.com/gamehublite/gamehub-worker)
- **gamehub_api repository:** [github.com/gamehublite/gamehub_api](https://github.com/gamehublite/gamehub_api)
- **gamehub-oss repository:** [github.com/gamehublite/gamehub-oss](https://github.com/gamehublite/gamehub-oss)
- **Deployed Worker:** [gamehub-api.secureflex.workers.dev](https://gamehub-api.secureflex.workers.dev)

---

## 📊 Stats

- **Total Repositories:** 3
- **Total Stars:** TBD
- **Languages:** TypeScript, JSON, Markdown
- **License:** MIT (educational purposes)
- **Status:** Active development

---

## 📧 Contact

For questions, issues, or discussions:
- Open an issue in the relevant repository
- Check repository documentation first
- Review existing issues before creating new ones

---

## 🙏 Acknowledgments

Built with:
- [Cloudflare Workers](https://workers.cloudflare.com/) - Edge computing platform
- [GitHub Pages](https://pages.github.com/) - Static hosting
- [apktool](https://apktool.org/) - APK reverse engineering
- Open source community tools and knowledge

Inspired by:
- Privacy research community
- Android reverse engineering community
- Open source transparency advocates

---

**GameHub Lite** - Privacy-respecting, transparent, self-hostable.

*Last updated: October 2025*
