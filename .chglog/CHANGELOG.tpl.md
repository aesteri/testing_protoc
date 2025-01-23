# CHANGELOG

All notable changes to this project will be documented in this file.

{{ range .Versions }}
---
## [{{ .Tag.Name }}] - {{ datetime "2006-01-02" .Tag.Date }}
{{ range .Commits }}
- {{ .Subject }} ({{ .Scope }})
{{ end }}
{{ end }}
---

This changelog was generated with ❤️ by [git-chglog](https://github.com/git-chglog/git-chglog).
