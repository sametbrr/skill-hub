[![GitHub release](https://img.shields.io/github/v/release/sametbrr/skill-hub?display_name=tag&sort=semver)](https://github.com/sametbrr/skill-hub/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

# skill-hub

Claude Code skill koleksiyonu — wiki yönetimi, konuşma kontrol noktaları, NotebookLM otomasyonu, proje keşfi, prompt mühendisliği ve README araçları.

> 🇬🇧 For English see [README.md](README.md)

---

## Hızlı Başlangıç

Herhangi bir eklentiyi doğrudan GitHub deposundan yükle:

```bash
claude plugin install github:sametbrr/llm-wiki-manager
```

Ardından Claude Code içinden çağır:

```
/llm-wiki-manager bootstrap
```

Çoğu eklenti için ek yapılandırma gerekmez.

---

## Özellikler

| Eklenti | Ne yapar |
|---|---|
| [llm-wiki-manager](llm-wiki-manager/) | Kişisel LLM wiki yönetimi: kaynak alma, çapraz referans, sorgulama, lint |
| [look-again](look-again/) | Konuşma kontrol noktalarını markdown olarak kaydet ve tam bağlamla devam et |
| [notebooklm](notebooklm/) | Google NotebookLM'e tam programatik erişim: not defterleri, podcast, quiz ve daha fazlası |
| [project-radar](project-radar/) | Günlük Türkçe HTML radar raporu: trend GitHub projeleri ve kalıcı takip listesi |
| [prompt-architect](prompt-architect/) | Her ham isteği 8 kapılı incelemeyle yapılandırılmış uzman promptuna dönüştür |
| [readme-standard](readme-standard/) | Tutarlı README.md + README.tr.md yapısını zorla: oluştur, denetle, düzelt ve TR senkronize et |

---

## Gereksinimler

- Claude Code CLI (en güncel sürüm)
- Eklentiye özgü gereksinimler her eklentinin kendi README dosyasında listelenir

---

## Kurulum

Her eklenti bağımsız bir GitHub deposudur. Ayrı ayrı yükle:

```bash
claude plugin install github:sametbrr/llm-wiki-manager
claude plugin install github:sametbrr/look-again
claude plugin install github:sametbrr/notebooklm
claude plugin install github:sametbrr/project-radar
claude plugin install github:sametbrr/prompt-architect
claude plugin install github:sametbrr/readme-standard
```

---

## Kullanım

Her eklenti, kurulumun ardından Claude Code tarafından otomatik olarak algılanan bir skill kaydeder. Tam kullanım ve yapılandırma için ilgili eklentinin README dosyasına bakın.

| Eklenti | Tetikleyici |
|---|---|
| llm-wiki-manager | `/llm-wiki-manager` veya "second brain", "wiki", "Memex" |
| look-again | `/look-again` |
| notebooklm | `/notebooklm` veya "X hakkında podcast oluştur" |
| project-radar | `/project-radar` veya "radar çalıştır" |
| prompt-architect | `/prompt-architect` veya "prompt yaz", "refine my prompt" |
| readme-standard | `/readme-standard` |

---

## Nasıl Çalışır

Bu hub'daki her eklenti aynı yapıyı izler:

```
eklenti-adı/
├── SKILL.md              → Claude Code'un yüklediği skill tanımı
├── .claude-plugin/
│   └── plugin.json       → marketplace metadata
├── assets/               → şablonlar ve statik kaynaklar
├── references/           → çalışma zamanında okunan referans belgeler
└── scripts/              → yardımcı betikler (gerektiğinde Python)
```

`SKILL.md` giriş noktasıdır — skill adını, açıklamasını ve Claude'un skill çağrıldığında izlediği talimatları tanımlar. `plugin.json` eklentiyi marketplace'e kaydeder.

---

## Proje Yapısı

```
skill-hub/
├── llm-wiki-manager/     → kişisel wiki yönetimi
├── look-again/           → konuşma kontrol noktaları
├── notebooklm/           → Google NotebookLM otomasyonu
├── project-radar/        → GitHub trend radarı
├── prompt-architect/     → uzman prompt mühendisliği
├── readme-standard/      → README standart uygulaması
└── .claude-plugin/
    └── marketplace.json  → hub düzeyinde marketplace indeksi
```

Her alt dizin aynı zamanda bağımsız bir git deposudur ve tek başına kullanılabilir.

---

## Lisans

MIT — bkz. [LICENSE](LICENSE).
