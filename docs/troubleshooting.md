# Troubleshooting

Problemas comuns com Sunshine + Moonlight, válidos para [Android](android.md) e [Fire Stick](firestick.md). Este é o único lugar onde ficam as regras de firewall e a lista de portas.

## Índice

- [Troubleshooting](#troubleshooting)
  - [Índice](#índice)
  - [Tarjas pretas continuam aparecendo](#tarjas-pretas-continuam-aparecendo)
  - [Erro: Falha ao iniciar Steam Big Picture (error 0)](#erro-falha-ao-iniciar-steam-big-picture-error-0)
    - [Portas do Sunshine (padrão)](#portas-do-sunshine-padrão)
    - [Se ainda falhar, confira](#se-ainda-falhar-confira)
  - [O PC não aparece no Moonlight](#o-pc-não-aparece-no-moonlight)
  - [Imagem travando ou com lag](#imagem-travando-ou-com-lag)

---

## Tarjas pretas continuam aparecendo

Identifique onde estão as barras:

| Onde | Causa provável | O que fazer |
|---|---|---|
| Em volta de **toda a imagem** (borda externa) | Resolução/proporção do stream | Revise [Configurar o display](sunshine-pc.md#configurar-o-display-evita-tarjas-pretas) e confirme **Optimize game settings: ON** |
| **Dentro** do jogo (barras no topo e na base da cena) | O próprio jogo renderiza em outra proporção | No jogo, configure a proporção e a resolução iguais às pedidas no Moonlight (por exemplo `16:9` e `1920×1080`) |

---

## Erro: Falha ao iniciar Steam Big Picture (error 0)

Mensagem completa:

```
Erro de Conexão
Falha ao iniciar Steam Big Picture (error 0)

Verifique o firewall e permita a(s) seguinte(s) para porta(s):
TCP 47984
TCP 47989
```

**O que significa:** o Moonlight alcançou o Sunshine, mas o Windows está bloqueando as portas que o Sunshine usa para a sessão. O problema não é o dispositivo nem o Steam.

**Correção:** abra o **PowerShell como Administrador** e rode:

```powershell
# Portas TCP
New-NetFirewallRule -DisplayName "Sunshine TCP" -Direction Inbound -Protocol TCP -LocalPort 47984,47989,48010 -Action Allow

# Portas UDP
New-NetFirewallRule -DisplayName "Sunshine UDP" -Direction Inbound -Protocol UDP -LocalPort 47998,47999,48000,48002,48010 -Action Allow
```

Depois feche o Moonlight por completo, abra de novo e inicie o Steam pelo PC listado.

### Portas do Sunshine (padrão)

| Protocolo | Porta | Uso |
|---|---|---|
| TCP | 47984 | HTTPS (pareamento e controle) |
| TCP | 47989 | HTTP |
| TCP | 47990 | Interface web (só acesso local) |
| TCP | 48010 | RTSP |
| UDP | 47998 | Vídeo |
| UDP | 47999 | Controle |
| UDP | 48000 | Áudio |
| UDP | 48002 | Microfone |

> Portas padrão do Sunshine. Se você alterou a porta base na configuração, todas elas se deslocam.

### Se ainda falhar, confira

- O Sunshine está rodando (serviço ativo ou ícone na bandeja).
- A rede do Windows está como **Privada**, não Pública. Em redes públicas o firewall é bem mais restritivo.
- Um antivírus ou firewall de terceiros não está bloqueando as portas.
- PC e dispositivo estão realmente na mesma rede/sub-rede (cuidado com rede de convidados, VLANs e repetidores).
- O IP do PC não mudou. Se o roteador usa DHCP, reserve um IP fixo para o PC.

---

## O PC não aparece no Moonlight

1. Confirme que o Sunshine está rodando e que `https://localhost:47990` abre no PC.
2. Confirme que PC e dispositivo estão na mesma rede e sub-rede.
3. Adicione manualmente pelo IP. Veja [Descobrir o IP do PC](sunshine-pc.md#descobrir-o-ip-do-pc).
4. Use apenas o IP, **sem** a porta `47990`.
5. Revise as regras de firewall da seção anterior.

---

## Imagem travando ou com lag

1. Reduza o **bitrate** primeiro.
2. Depois reduza a resolução ou os FPS.
3. Prefira Wi-Fi 5 GHz no dispositivo e Ethernet no PC.
4. Aproxime o dispositivo do roteador.
5. Feche programas pesados no PC que disputem a GPU com o jogo.
