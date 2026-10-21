# Moonlight no Android

> **Pré-requisito:** [Sunshine instalado e funcionando no PC](sunshine-pc.md).

Guia para transmitir jogos do PC para um celular ou tablet Android.

## Requisitos

| Item | Detalhe |
|---|---|
| Aparelho | Celular ou tablet Android com decodificação de vídeo por hardware |
| Rede | Wi-Fi 5 GHz ou Wi-Fi 6, na mesma rede do PC |
| Ideal | PC no cabo Ethernet e roteador próximo do aparelho |

## 1. Instale o Moonlight

Na **Google Play Store**, pesquise por **Moonlight Game Streaming** e instale.

## 2. Conecte à mesma rede do PC

Conecte o aparelho ao Wi-Fi do PC. Se o roteador separa as redes 2.4 GHz e 5 GHz, use a de **5 GHz**.

## 3. Adicione o PC

Abra o Moonlight.

- Se o PC aparecer sozinho, toque nele.
- Se não aparecer, toque em **+** (Add PC) e digite o IP. Veja como descobri-lo em [Descobrir o IP do PC](sunshine-pc.md#descobrir-o-ip-do-pc).

## 4. Faça o pareamento

Siga o passo a passo em [Parear um dispositivo](sunshine-pc.md#parear-um-dispositivo). O Moonlight mostra o PIN e você o digita na aba **PIN** do Sunshine.

## 5. Ajuste as configurações

Abra as configurações do Moonlight (ícone de engrenagem) e ajuste:

| Configuração | Valor recomendado |
|---|---|
| Resolução | A da tela do aparelho, ou 1080p |
| FPS | 60, ou 90/120 se a tela e o PC aguentarem |
| Codec | HEVC/H.265, ou AV1 se o aparelho e a GPU suportarem |
| Bitrate | 20–40 Mbps em Wi-Fi 5 GHz |
| Optimize game settings | **ON** (obrigatório para evitar tarjas) |

Se o vídeo travar ou picotar, reduza o bitrate primeiro. Depois reduza a resolução ou os FPS.

## 6. Resolva as tarjas pretas

Celulares costumam ter telas alongadas (por exemplo 20:9), diferentes dos 16:9 de monitores e jogos.

1. Configure o Sunshine para resolução e refresh `Auto`. Veja [Configurar o display](sunshine-pc.md#configurar-o-display-evita-tarjas-pretas).
2. No Moonlight, escolha uma resolução com a proporção da tela do aparelho (opção de resolução personalizada) e deixe **Optimize game settings** ligado.
3. Se preferir manter 16:9, aceite as barras laterais. Elas evitam que a imagem fique esticada ou cortada.

Se as barras estiverem **dentro do jogo**, ajuste a proporção no próprio jogo. Veja o [diagnóstico](troubleshooting.md#tarjas-pretas-continuam-aparecendo).

## 7. Controle

| Opção | Observação |
|---|---|
| Controle Bluetooth ou USB | Melhor experiência. Pareie no Android antes de abrir o Moonlight |
| Controles na tela | Úteis para testes, menos precisos para jogos de ação |
| Toque e mouse | O toque funciona como touchpad ou como toque direto, conforme a configuração |

## 8. Inicie um jogo

Toque no PC no Moonlight e escolha `Steam Big Picture` ou `Desktop`.

## Problemas?

Erros de conexão, firewall e portas estão em [troubleshooting.md](troubleshooting.md).
