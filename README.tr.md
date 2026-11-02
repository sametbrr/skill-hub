[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/agentskills.io-compatible-blue)](https://agentskills.io)

[Hızlı Başlangıç](#hızlı-başlangıç) • [Özellikler](#özellikler) • [Kurulum](#kurulum) • [Kullanım](#kullanım) • [Nasıl Çalışır](#nasıl-çalışır) • [Katkıda Bulunma](#katkıda-bulunma)

# skill-hub

Claude Code ve OpenAI Codex için plugin marketplace'i: wiki yönetimi, konuşma checkpoint'leri, proje keşfi, modele duyarlı prompt mühendisliği, GitHub hesap araçları ve şifreli secret senkronizasyonu.

> 🇬🇧 For English see [README.md](README.md)

---

## Hızlı Başlangıç

```bash
# Claude Code
claude plugin marketplace add sametbrr/skill-hub
claude plugin install llm-wiki-manager@skill-hub

# Codex
codex plugin marketplace add sametbrr/skill-hub
codex plugin add llm-wiki-manager@skill-hub
```

Sonra doğal dille isteyin, örn. *"burada bir LLM wiki kur"*. Çoğu plugin başka ayar gerektirmez.

---

## Özellikler

| Plugin | Ne yapar | Claude Code | Codex |
|---|---|:---:|:---:|
| [llm-wiki-manager](https://github.com/sametbrr/llm-wiki-manager) | LLM'in yönettiği kişisel wiki: kaynak ekleme, sayfalar arası referans, kaynaklı sorgu, lint | ✓ | ✓ |
| [look-again](https://github.com/sametbrr/look-again) | Konuşma checkpoint'lerini markdown olarak kaydeder, tam bağlamla devam ettirir; iki ajan aynı klasörü kullanır | ✓ | ✓ |
| [prompt-architect](https://github.com/sametbrr/prompt-architect) | Kaba bir isteği, tespit edilen Claude ya da OpenAI/Codex modeline göre ayarlanmış uzman prompt'a çevirir; 12 kapılı inceleme | ✓ | ✓ |
| [github-manager](https://github.com/sametbrr/github-manager) | Herhangi bir GitHub hesabını denetler ve güçlendirir: profil, profil README'si, açıklamalar, topic'ler, README'ler, release workflow'ları (readme-standard dahil) | ✓ | ✓ |
| [crypt-sync](https://github.com/sametbrr/crypt-sync) | `.env` ve secret dosyalarını git'te age ile şifreli tutar, makineler arası senkronlar — **`npm install -g crypt-sync` gerekir** | ✓ | ✓ |
| [project-radar](https://github.com/sametbrr/project-radar) | GitHub trend projelerinin günlük Türkçe HTML radar raporu ve kalıcı izleme listesi | ✓ | — |

Her plugin girdisi bir release tag'ine sabitlenmiştir; kurulum ve güncellemeler yalnızca yayınlanmış sürümleri alır.

---

## Gereksinimler

- Claude Code ya da OpenAI Codex CLI (güncel)
- Plugin'e özel gereksinimler her plugin'in kendi README'sinde
- `crypt-sync` ayrıca CLI'nin `PATH`'te olmasını ister: `npm install -g crypt-sync` (Node.js 22 veya üzeri, LTS). Plugin ajan katmanıdır; şifreleme motoru npm paketidir

---

## Kurulum

**Claude Code**

```bash
claude plugin marketplace add sametbrr/skill-hub
claude plugin install <plugin>@skill-hub          # örn. prompt-architect@skill-hub
claude plugin marketplace update skill-hub        # yeni sürümleri al
```

**Codex**

```bash
codex plugin marketplace add sametbrr/skill-hub
codex plugin add <plugin>@skill-hub
codex plugin marketplace upgrade skill-hub        # yeni sürümleri al
```

**Diğer Agent Skills istemcileri** (Copilot, Cursor, Gemini CLI, …)

```bash
gh skill install sametbrr/<plugin> --agent <agent-name>
```

---

## Kullanım

Skill'ler doğal dille tetiklenir. İsterseniz açıkça da seçebilirsiniz (Claude Code'da `/plugin:skill`, Codex'te skill seçici ya da skill anma). Ayrıntılı kullanım her plugin'in README'sinde.

| Plugin | Örnek tetikleyiciler |
|---|---|
| llm-wiki-manager | "second brain", "bunu wiki'me ekle", "wiki'yi kontrol et" |
| look-again | "look again", "look again list", "kaldığımız yerden devam et" |
| prompt-architect | "prompt yaz", "refine my prompt", "bunu Opus 5.5 / GPT-6.1 için yaz" |
| github-manager | `gh-onboard`, `gh-audit`, `gh-normalize`, `profile-bio`, `profile-readme`, `readme-standard`, `release-workflow` |
| crypt-sync | ".env şifrele", "secret sync", "encrypt my env files" |
| project-radar | "radar çalıştır", "github trending raporu" |

---

## Nasıl Çalışır

Her plugin kendi semver tag'leri olan ayrı bir GitHub reposudur ve iki ortamda da çalışır:

```
plugin-name/
├── .claude-plugin/plugin.json   → Claude Code manifesti
├── .codex-plugin/plugin.json    → Codex manifesti (aynı ad ve sürüm)
├── skills/<skill>/SKILL.md      → her skill için bir klasör; references/, scripts/, assets/ ile
├── agents/, hooks/              → isteğe bağlı Claude Code alt ajanları ve hook'ları
├── AGENTS.md                    → repoda çalışan her ajan için rehber (CLAUDE.md bunu içe aktarır)
└── README.md / README.tr.md
```

Bu repo yalnızca `.claude-plugin/marketplace.json` dosyasını tutar; Claude Code ve Codex ikisi de bu dosyayı okur. Her girdi bir plugin reposunu bir release tag'inde gösterir.

---

## Proje Yapısı

```
skill-hub/
├── .claude-plugin/
│   └── marketplace.json   → Claude Code ve Codex'in okuduğu katalog
├── README.md / README.tr.md
└── LICENSE
```

Yerel geliştirme için plugin repoları katalogun yanına klonlanabilir (`skill-hub/<plugin>/`); burada git tarafından yok sayılırlar.

---

## Katkıda Bulunma

- Sorular ve fikirler: [Discussions](https://github.com/sametbrr/skill-hub/discussions)
- Hatalar: [issue takibi](https://github.com/sametbrr/skill-hub/issues)
- Pull request'ler: önce [katkı rehberini](https://github.com/sametbrr/.github/blob/main/CONTRIBUTING.md) okuyun
- Güvenlik bildirimleri: herkese açık issue yerine [güvenlik politikasını](https://github.com/sametbrr/skill-hub/security/policy) izleyin

---

## Lisans

MIT — bkz. [LICENSE](LICENSE).
