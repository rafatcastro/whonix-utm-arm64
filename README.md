# Whonix UTM ARM64 (Apple Silicon)

Imagens **Whonix 18.2.4.3** (Debian 13 Trixie, `arm64`) compiladas com `derivative-maker` para **UTM** em Macs Apple Silicon, já com os discos convertidos para **`.qcow2`** (corrigindo o erro `QEMU error: drive0, #block530: Invalid argument` no UTM 4.x / APFS).

> Os arquivos `.utm.tar.gz` (~996 MB e ~1,3 GB) excedem o limite de 100 MB por arquivo do Git normal no GitHub, portanto estão hospedados na aba **Releases** (`v18.2.4.3-arm64`).

## Imagens na Release `v18.2.4.3-arm64`

| Arquivo | Formato do disco | Tamanho | SHA-256 |
| --- | --- | --- | --- |
| `Whonix-Gateway-LXQt.utm.tar.gz` | `qcow2` | ~996 MB | `b40524925ad470631f353f52d920c6cd5b74d243cee7756167a7950aa070c709` |
| `Whonix-Workstation-LXQt.utm.tar.gz` | `qcow2` | ~1.3 GB | `d8cd263abcb24523f58d7caff7f897058e2d998dc04f0e55eea443ae3ae5b0f1` |

## Como baixar e importar no UTM (macOS)

```bash
mkdir -p ~/Downloads/whonix-utm && cd ~/Downloads/whonix-utm
gh release download v18.2.4.3-arm64 --repo rafatcastro/whonix-utm-arm64
shasum -a 256 -c SHA256SUMS.txt

tar -xzf Whonix-Gateway-LXQt.utm.tar.gz
tar -xzf Whonix-Workstation-LXQt.utm.tar.gz

open -a UTM Whonix-Gateway-LXQt.utm
open -a UTM Whonix-Workstation-LXQt.utm
```

## Ordem de inicialização

1. Inicie primeiro o **Whonix-Gateway-LXQt** (abre a rede interna na porta `8010` e conecta ao Tor).
2. Depois inicie o **Whonix-Workstation-LXQt** (conecta-se ao Gateway via `127.0.0.1:8010`).
