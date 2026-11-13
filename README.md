# TheVault Login

A login-only visual customization for TheVault's Unraid sign-in page.

The plugin keeps Unraid's native authentication, sessions, SSO, rate limiting, and password recovery intact. It changes only the presentation layer: a responsive split-screen login with the stock form on the left, locally embedded homelab artwork on the right, and a subtle Unraid version footer with the host's current uptime underneath.

## Install

Use the stable plugin URL:

```text
https://raw.githubusercontent.com/gunner007cd/thevault-login/main/thevault.login.plg
```

For an existing local install, replace `/boot/config/plugins/thevault.login.plg` with the hosted version and reinstall it through Unraid's plugin manager.

## Design

- Login page only; the rest of the Unraid webGUI is untouched.
- Background artwork is embedded directly into the login HTML at install time, so it does not depend on pre-authenticated asset routing.
- The running Unraid version is read from `/etc/unraid-version`.
- Uptime is read from Linux `/proc/uptime` when the login page is requested, so it reflects TheVault's actual runtime rather than the age of the browser tab.
- The installer is idempotent and removes older TheVault login hooks before applying the current one.

Author: Christopher Deal
