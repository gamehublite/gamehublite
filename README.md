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
