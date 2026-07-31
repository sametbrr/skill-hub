[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

# skill-hub

Claude Code skill koleksiyonu — wiki yönetimi, konuşma kontrol noktaları, proje keşfi, prompt mühendisliği ve GitHub hesap yönetimi.

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
| [llm-wiki-manager](https://github.com/sametbrr/llm-wiki-manager) | Kişisel LLM wiki yönetimi: kaynak alma, çapraz referans, sorgulama, lint |
| [look-again](https://github.com/sametbrr/look-again) | Konuşma kontrol noktalarını markdown olarak kaydet ve tam bağlamla devam et |
| [project-radar](https://github.com/sametbrr/project-radar) | Günlük Türkçe HTML radar raporu: trend GitHub projeleri ve kalıcı takip listesi |
| [prompt-architect](https://github.com/sametbrr/prompt-architect) | Her ham isteği modele duyarlı, 11 kapılı incelemeyle yapılandırılmış uzman promptuna dönüştür |
| [github-manager](https://github.com/sametbrr/github-manager) | Bir GitHub hesabını uçtan uca denetle ve düzelt: profil alanları, profil README, repo açıklamaları, topics ve proje README'leri (readme-standard'ı içerir) |

---

## Gereksinimler

- Claude Code CLI (en güncel sürüm)
- Eklentiye özgü gereksinimler her eklentinin kendi README dosyasında listelenir

---

## Kurulum

**Seçenek 1 — Marketplace (önerilen):** Hub'ı bir kez kaydet, ardından istediğin eklentiyi adıyla yükle.

```bash
claude plugin marketplace add sametbrr/skill-hub
claude plugin install llm-wiki-manager@sametbrr/skill-hub
```

**Seçenek 2 — Tek tek kurulum:** Her eklentiyi doğrudan kendi deposundan yükle.

```bash
claude plugin install github:sametbrr/llm-wiki-manager
claude plugin install github:sametbrr/look-again
claude plugin install github:sametbrr/project-radar
claude plugin install github:sametbrr/prompt-architect
claude plugin install github:sametbrr/github-manager
```

---

## Kullanım

Her eklenti, kurulumun ardından Claude Code tarafından otomatik olarak algılanan bir skill kaydeder. Tam kullanım ve yapılandırma için ilgili eklentinin README dosyasına bakın.

| Eklenti | Tetikleyici |
|---|---|
| llm-wiki-manager | `/llm-wiki-manager` veya "second brain", "wiki", "Memex" |
| look-again | `/look-again` |
| project-radar | `/project-radar` veya "radar çalıştır" |
| prompt-architect | `/prompt-architect` veya "prompt yaz", "refine my prompt" |
| github-manager | `/gh-onboard`, `/gh-audit`, `/gh-normalize`, `/profile-bio`, `/profile-readme`, `/readme-standard` |

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
├── project-radar/        → GitHub trend radarı
├── prompt-architect/     → uzman prompt mühendisliği
├── github-manager/       → GitHub hesap & repo yönetimi
└── .claude-plugin/
    └── marketplace.json  → hub düzeyinde marketplace indeksi
```

Her alt dizin aynı zamanda bağımsız bir git deposudur ve tek başına kullanılabilir.

---

## Lisans

MIT — bkz. [LICENSE](LICENSE).
