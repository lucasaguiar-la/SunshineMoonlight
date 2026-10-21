# Streaming de jogos do PC com Sunshine + Moonlight

Guias práticos para transmitir jogos do seu PC com Windows para o **Android** ou para a TV com um **Fire TV Stick**. O PC usa o **Sunshine** e o dispositivo usa o **Moonlight**.

## Como funciona

```
PC (Sunshine) ──── rede local ────> Dispositivo (Moonlight) ────> Tela
```

O Sunshine captura a tela do PC e envia o vídeo. O Moonlight recebe, decodifica e exibe. Os comandos do controle fazem o caminho inverso.

## Por onde começar

1. **Instale o Sunshine no PC:** [docs/sunshine-pc.md](docs/sunshine-pc.md). Este passo é obrigatório para todos os dispositivos.
2. **Escolha o seu dispositivo** na tabela abaixo.
3. **Algo deu errado?** Consulte o [troubleshooting](docs/troubleshooting.md).

## Sumário dos guias

| Guia | Quando usar |
|---|---|
| [Sunshine no PC](docs/sunshine-pc.md) | Sempre, é o pré-requisito de tudo |
| [Android](docs/android.md) | Celular ou tablet Android |
| [Fire TV Stick](docs/firestick.md) | Fire TV Stick 3ª geração (2020) na TV |
| [Troubleshooting](docs/troubleshooting.md) | Firewall, portas, rede, tarjas pretas |

## Comparativo rápido

| | Android | Fire Stick (3ª ger.) |
|---|---|---|
| Resolução máxima | Depende do aparelho | 1080p / 60 FPS |
| Rede ideal | Wi-Fi 5 GHz ou 6 | Wi-Fi 5 GHz |
| Controle | Toque, Bluetooth ou USB | Bluetooth |
| Instalação do Moonlight | Play Store | Amazon Appstore (ou APK) |

## Requisitos gerais

| Item | Detalhe |
|---|---|
| PC | Windows 10/11 com GPU NVIDIA, AMD ou Intel (encoder de vídeo por hardware) |
| Rede | PC e dispositivo na mesma rede local |
| Ideal | PC no cabo Ethernet e dispositivo no Wi-Fi 5 GHz |

## Estrutura do repositório

```
.
├── README.md
└── docs/
    ├── sunshine-pc.md
    ├── android.md
    ├── firestick.md
    └── troubleshooting.md
```

## Referências

- [Documentação do Sunshine](https://docs.lizardbyte.dev/projects/sunshine/)
- [Moonlight (GitHub)](https://github.com/moonlight-stream)
- [Especificações do Fire TV Stick (Amazon Developer)](https://developer.amazon.com/docs/fire-tv/device-specifications.html)

## Contribuindo

Testou em outro dispositivo, outra versão do Sunshine ou encontrou um erro diferente? Abra uma issue ou um pull request.
