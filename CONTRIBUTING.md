# Contribuindo

Obrigado por querer ajudar! Este repositório reúne guias para transmitir jogos de um PC com Windows usando **Sunshine** (PC) e **Moonlight** (dispositivo). Esta página explica como adicionar um **novo dispositivo** (por exemplo Android TV, iOS, Apple TV, Raspberry Pi ou Steam Deck) ou corrigir um guia existente.

## Tipos de contribuição

- **Novo dispositivo:** um novo guia em `docs/`.
- **Correção ou melhoria:** erro de digitação, passo desatualizado, link quebrado.
- **Teste em outro cenário:** outro modelo de aparelho ou outra versão do Sunshine. Se não quiser escrever um guia, abra uma issue com o resultado.

## Estrutura do repositório

```
.
├── README.md
├── CONTRIBUTING.md
└── docs/
    ├── sunshine-pc.md       # pré-requisito de tudo (lado do PC)
    ├── android.md
    ├── firestick.md
    └── troubleshooting.md   # firewall, portas, rede, tarjas
```

## Regras de organização

1. **Cada informação fica em um só lugar.**
   - Instalação do Sunshine, IP do PC, pareamento e configuração de display ficam em `sunshine-pc.md`.
   - Firewall, portas e diagnóstico de rede ficam em `troubleshooting.md`.
   - O guia do dispositivo **só linka** para esses arquivos. Não copie o conteúdo.
2. **Um arquivo por dispositivo:** `docs/<dispositivo>.md`.
3. **Nomes de arquivo** em minúsculas, sem acentos e sem espaços. Exemplo: `android-tv.md`, `steam-deck.md`.
4. **Links relativos.** O README usa `docs/arquivo.md`. Os arquivos dentro de `docs/` usam só `arquivo.md`.
5. **Dados verificados.** Só inclua o que você testou ou que tenha fonte oficial. Se a informação varia entre versões, diga isso no texto.

## Como adicionar um novo dispositivo

### 1. Faça o fork e crie uma branch

```bash
git clone https://github.com/<seu-usuario>/<repositorio>.git
cd <repositorio>
git checkout -b docs/adicionar-<dispositivo>
```

### 2. Crie o guia em `docs/<dispositivo>.md`

Use o modelo abaixo e mantenha esta ordem de seções.

````markdown
# Moonlight no <Dispositivo>

> **Pré-requisito:** [Sunshine instalado e funcionando no PC](sunshine-pc.md).

Uma frase dizendo para quem é o guia.

## Requisitos

| Item | Detalhe |
|---|---|
| Aparelho | Modelo, versão do sistema, decodificação por hardware |
| Rede | Wi-Fi ou Ethernet recomendados |
| Ideal | Melhor cenário de uso |

## 1. Instale o Moonlight

Onde baixar (loja oficial primeiro; APK ou outro método só se necessário).

## 2. Conecte à mesma rede do PC

## 3. Adicione o PC

Link para [Descobrir o IP do PC](sunshine-pc.md#descobrir-o-ip-do-pc).

## 4. Faça o pareamento

Link para [Parear um dispositivo](sunshine-pc.md#parear-um-dispositivo).

## 5. Ajuste as configurações

| Configuração | Valor recomendado |
|---|---|
| Resolução | |
| FPS | |
| Codec | |
| Bitrate | |
| Optimize game settings | **ON** |

## 6. Resolva as tarjas pretas

Link para [Configurar o display](sunshine-pc.md#configurar-o-display-evita-tarjas-pretas)
e o valor de resolução específico deste dispositivo.

## 7. Controle

Como conectar e usar controles neste dispositivo.

## 8. Inicie um jogo

## Problemas?

Link para [troubleshooting.md](troubleshooting.md).
````

### 3. Atualize os arquivos que listam dispositivos

- **`README.md`:**
  - Adicione uma linha na tabela **Sumário dos guias**.
  - Adicione uma coluna na tabela **Comparativo rápido**.
  - Atualize a seção **Estrutura do repositório**.
- **`docs/sunshine-pc.md`:** adicione uma linha na tabela de resolução por dispositivo, na seção **Configurar o display**.
- **`docs/troubleshooting.md`:** só altere se o dispositivo tiver um problema específico. Nesse caso, crie uma seção nova em vez de duplicar texto.

### 4. Confira antes de abrir a PR

Use esta lista:

- [ ] O guia segue o modelo e a ordem de seções.
- [ ] Testei os passos no dispositivo real (ou citei a fonte oficial).
- [ ] Não dupliquei conteúdo de `sunshine-pc.md` nem de `troubleshooting.md`.
- [ ] Todos os links relativos abrem e as âncoras funcionam.
- [ ] O nome do arquivo está em minúsculas, sem acentos e sem espaços.
- [ ] O README e a tabela de dispositivos em `sunshine-pc.md` foram atualizados.
- [ ] Não incluí senhas, IPs públicos, tokens ou prints com dados pessoais.

### 5. Abra a Pull Request

```bash
git add .
git commit -m "[ADD]: Adiciona guia para <dispositivo>"
git push origin
```

Abra a PR no GitHub e descreva:

- Qual dispositivo e modelo foram testados.
- Versão do sistema do dispositivo e do Sunshine/Moonlight usadas.
- Qualquer limitação conhecida.

## Padrão de commits

Use mensagens curtas no formato `[TIPO]: Descrição`:

| Tipo | Quando usar |
|---|---|
| `ADD` | Novo guia ou alteração de texto |
| `FIX` | Correção de erro, link ou comando |
| `CHORE` | Organização, renomeações, ajustes sem mudar conteúdo |

Exemplos: `[ADD]: Adiciona guia para Android TV`, `[FIX]: Corrige âncora do troubleshooting`.

## Estilo de escrita

- Frases curtas e passos numerados.
- Comandos e nomes de arquivos entre crases.
- Blocos de código com a linguagem indicada (` ```powershell `).
- Tabelas para configurações e requisitos.
- Avisos em citações (`> Aviso`).
- Seja específico: "toque em **Add PC**" é melhor que "adicione o PC".

## Reportando problemas

Sem tempo para escrever uma PR? Abra uma **issue** com:

- Dispositivo e modelo.
- Versão do Sunshine e do Moonlight.
- O que você esperava e o que aconteceu.
- Mensagem de erro completa, se houver.

## Código de conduta

Seja respeitoso e objetivo. Críticas devem ser sobre o conteúdo, nunca sobre as pessoas.
