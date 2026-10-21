# Moonlight no Fire TV Stick (3ª geração, 2020)

> **Pré-requisito:** [Sunshine instalado e funcionando no PC](sunshine-pc.md).

Guia para transmitir jogos do PC para a TV com um **Fire TV Stick 3ª geração**.

## Requisitos

| Item | Detalhe |
|---|---|
| Streaming | Fire TV Stick 3ª geração (1080p / 60 FPS, Wi-Fi 5 GHz, Fire OS 7) |
| Rede | PC e Fire Stick na mesma rede local |
| Ideal | PC no cabo Ethernet, Fire Stick no Wi-Fi 5 GHz |

O Fire Stick 3ª geração é um dispositivo 1080p/60. 1440p ou 4K não irão funcionar nele.

## 1. Conecte o Fire Stick

Ligue o Fire Stick na TV, faça a configuração inicial e conecte-o à **mesma rede do PC**. Se o roteador separa as redes 2.4 GHz e 5 GHz, use a de **5 GHz**.

## 2. Instale o Moonlight

No Fire Stick: **Pesquisar → Moonlight Game Streaming → Instalar**.

Tente pela Amazon Appstore primeiro. Só recorra a APK (sideload) se não encontrar o app na loja.

## 3. Adicione o PC

Abra o Moonlight no Fire Stick.

- Se o PC aparecer sozinho, selecione-o.
- Se não aparecer, use **+ Add PC** e digite o IP. Veja como descobri-lo em [Descobrir o IP do PC](sunshine-pc.md#descobrir-o-ip-do-pc).

## 4. Faça o pareamento

Siga o passo a passo em [Parear um dispositivo](sunshine-pc.md#parear-um-dispositivo). O Moonlight mostra o PIN e você o digita na aba **PIN** do Sunshine.

## 5. Ajuste as configurações

| Configuração | Valor |
|---|---|
| Resolução | 1920×1080 |
| FPS | 60 |
| Codec | HEVC / H.265, se disponível |
| Bitrate | 30–40 Mbps |
| Optimize game settings | **ON** (obrigatório para evitar tarjas) |

## 6. Resolva as tarjas pretas

Configure o Sunshine com resolução e refresh `Auto`. Veja [Configurar o display](sunshine-pc.md#configurar-o-display-evita-tarjas-pretas).

No Moonlight, use `1920×1080`, `60 FPS` e **Optimize game settings: ON**.

Fluxo resultante:

```
Moonlight pede 1080p60 -> Sunshine muda o Windows para 1080p -> jogo renderiza em 16:9 -> TV sem tarjas
```

Se as tarjas continuarem, veja o [diagnóstico](troubleshooting.md#tarjas-pretas-continuam-aparecendo).

## 7. Inicie um jogo

Selecione o PC no Moonlight e escolha `Steam Big Picture` ou `Desktop`.

## Configuração recomendada (resumo)

| Configuração | Valor |
|---|---|
| Resolução (Moonlight) | 1920×1080 |
| FPS | 60 |
| Codec | HEVC / H.265, se disponível |
| Bitrate | 30–40 Mbps |
| Optimize game settings | ON |
| Resolução e refresh (Sunshine) | Auto |
| PC | Ethernet |
| Fire Stick | Wi-Fi 5 GHz |

## Problemas?

Erros de conexão, firewall e portas estão em [troubleshooting.md](troubleshooting.md).
