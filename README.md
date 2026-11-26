# Whonix UTM ARM64 (Apple Silicon)

Imagens **Whonix 18.2.4.3** (Debian 13 Trixie, `arm64`) compiladas com `derivative-maker` para **UTM** em Macs Apple Silicon.

> Os arquivos `.utm.tar.gz` (998 MB e 1,3 GB) excedem o limite de 100 MB por arquivo do Git normal no GitHub, portanto estão hospedados na aba **Releases** (`v18.2.4.3-arm64`).

## Imagens na Release `v18.2.4.3-arm64`

| Arquivo | Tamanho | SHA-256 |
| --- | --- | --- |
| `Whonix-Gateway-LXQt.utm.tar.gz` | ~998 MB | `ec2aa3d00c836d06d3007479389f2919904c521ae5ef6a9bd5b3701dfbb9330f` |
| `Whonix-Workstation-LXQt.utm.tar.gz` | ~1.3 GB | `169d5445975c3adf0e7ae5837cdfbe486ff29fdb613b88a6ee48e232f8d6d44b` |

## Como baixar e importar no UTM (macOS)

```bash
mkdir -p ~/Downloads/whonix-utm && cd ~/Downloads/whonix-utm
gh release download v18.2.4.3-arm64 --repo rafatcastro/whonix-utm-arm64
shasum -a 256 -c SHA256SUMS.txt

tar --strip-components=4 -xzf Whonix-Gateway-LXQt.utm.tar.gz
tar --strip-components=4 -xzf Whonix-Workstation-LXQt.utm.tar.gz

open -a UTM Whonix-Gateway-LXQt.utm
open -a UTM Whonix-Workstation-LXQt.utm
```

## Ordem de inicialização

1. Inicie primeiro o **Whonix-Gateway-LXQt** (abre a rede interna na porta `8010` e conecta ao Tor).
2. Depois inicie o **Whonix-Workstation-LXQt** (conecta-se ao Gateway via `127.0.0.1:8010`).
