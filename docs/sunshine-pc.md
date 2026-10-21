# Sunshine no PC (pré-requisito)

O Sunshine é o servidor de streaming. Ele roda no PC e envia a imagem para o Moonlight. **Este guia vale para todos os dispositivos.** Faça-o antes de [Android](android.md) ou [Fire Stick](firestick.md).

## Antes de começar

- Atualize o **driver de vídeo**. O Sunshine usa o encoder de hardware da placa (NVENC na NVIDIA, AMF na AMD, Quick Sync na Intel).
- Se for jogar pela Steam, deixe-a instalada e com login feito no PC.

## Instalar

**Opção A: instalador**

1. Abra a [página de releases do Sunshine](https://github.com/LizardByte/Sunshine/releases/latest).
2. Baixe o instalador para Windows (arquivo `.exe`).
3. Execute como administrador e avance com as opções padrão.
4. Se o instalador oferecer iniciar o Sunshine como serviço, mantenha marcado. Assim ele sobe junto com o Windows.

**Opção B: winget**

No PowerShell:

```powershell
winget install LizardByte.Sunshine
```

## Primeiro acesso

1. Abra `https://localhost:47990` no navegador do PC.
2. O navegador vai avisar que o certificado não é confiável. É esperado: o Sunshine usa certificado autoassinado. Prossiga mesmo assim.
3. Crie o **usuário e a senha** de administrador e guarde-os.

## Conferir se está funcionando

- A interface web abre normalmente.
- Em **Applications**, existem as entradas `Desktop` e `Steam Big Picture`. São elas que vão aparecer no Moonlight.

O instalador costuma criar as regras de firewall sozinho. Se mais adiante o Moonlight não conseguir conectar, veja o [troubleshooting](troubleshooting.md).

## Descobrir o IP do PC

Você vai precisar dele se o PC não aparecer sozinho no Moonlight. No PowerShell ou CMD:

```powershell
ipconfig
```

Anote o **IPv4** do adaptador em uso. Exemplo: `192.168.15.2`.

> Se o roteador usa DHCP, reserve um IP fixo para o PC. Assim o endereço não muda.

## Parear um dispositivo

O pareamento é igual para qualquer dispositivo. Ele é iniciado pelo Moonlight.

1. No Moonlight, adicione o PC (automaticamente ou pelo IP). O app vai exibir um **PIN** de 4 dígitos.
2. No PC, abra `https://localhost:47990`.
3. Vá na aba **PIN**, digite o código e confirme.

Pronto: o PC passa a aparecer no Moonlight com seus aplicativos e jogos.

> **Não** coloque a porta `47990` no Moonlight. Ela é só da interface web do Sunshine.

## Configurar o display (evita tarjas pretas)

**Causa das tarjas:** o monitor do PC tem outra proporção (por exemplo 2560×1440, 3440×1440 ou 2560×1080) e a tela do dispositivo é diferente. O stream sai numa resolução que não casa com ela.

**Solução:** o Moonlight pede a resolução desejada e o Sunshine troca a resolução do Windows durante a sessão. Ao encerrar, ele restaura a resolução original do monitor.

**No Sunshine** (`https://localhost:47990`, seção de configuração de display):

- Resolução: `Auto` (`dd_resolution_option = auto`)
- Taxa de atualização: `Auto` (`dd_refresh_rate_option = auto`)

> Se essas opções estiverem desabilitadas, ative antes a configuração do dispositivo de exibição (`dd_configuration_option`). Os nomes exatos variam um pouco entre versões do Sunshine.

**No Moonlight**, o que muda por dispositivo é o valor pedido. Ative sempre **Optimize game settings**, que é obrigatório para o Sunshine trocar a resolução.

| Dispositivo | Resolução no Moonlight | Guia |
|---|---|---|
| Fire Stick (TV 1080p) | 1920×1080 | [firestick.md](firestick.md) |
| Android | Resolução da tela do aparelho (ou 1080p) | [android.md](android.md) |

Fluxo resultante:

```
Moonlight pede a resolução -> Sunshine muda o Windows para ela -> jogo renderiza na proporção certa -> sem tarjas
```

Se as tarjas continuarem, veja a [tabela de diagnóstico](troubleshooting.md#tarjas-pretas-continuam-aparecendo).

## Próximo passo

Escolha o seu dispositivo: [Android](android.md) ou [Fire Stick](firestick.md).
