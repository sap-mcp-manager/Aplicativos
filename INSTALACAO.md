# Como instalar o SAP MCP Manager no Windows

Arquivo único: **`SAPMCPManager-Setup-1.0.6.exe`** (~88 MB)



## ⚠ Aviso de "Download suspeito" / SmartScreen — é normal

Ao baixar e executar, o Windows vai exibir **"Download suspeito bloqueado"** ou **"O Windows protegeu o seu PC"**. Isso acontece com todo aplicativo Windows novo que ainda não tem reputação suficiente no Microsoft SmartScreen.

**O arquivo é seguro** — ele é assinado apenas com a identidade do fabricante (Thinking IT). Conforme mais pessoas baixarem e instalarem, o Windows automaticamente aprende que é confiável e o aviso desaparece.

## Instalação passo a passo

### 1. Baixar o instalador

Arquivo: `SAPMCPManager-Setup-1.0.6.exe` (~88 MB)

### 2. Desbloquear o download (Edge/Chrome)

Quando o browser mostrar **"Download suspeito bloqueado"**:

**No Edge:**
1. Clique nos 3 pontinhos (⋮) ao lado do arquivo na barra de downloads
2. Selecione **"Manter"**
3. Confirme em **"Manter mesmo assim"**

**No Chrome:**
1. Clique na setinha (⌃) ao lado do arquivo
2. Selecione **"Manter"**

### 3. Executar o instalador

Ao dar duplo clique, o **Windows SmartScreen** vai abrir uma tela azul:

> **"O Windows protegeu o seu PC"**
> _"O Microsoft Defender SmartScreen impediu a inicialização de um aplicativo não reconhecido."_

**Passos:**
1. Clique em **"Mais informações"** (link pequeno)
2. Aparecem os detalhes:
   - **Aplicativo:** SAPMCPManager-Setup-1.0.6.exe
   - **Editor:** Thinking IT
3. Clique em **"Executar assim mesmo"** (botão que aparece)

### 4. Continuar a instalação

1. Aceite o controle de conta do usuário (UAC)
2. Escolha onde instalar (padrão: `C:\Users\<você>\AppData\Local\Programs\SAP MCP Manager\`)
3. Marque "Criar atalho na área de trabalho" se quiser
4. Conclua

### 5. Abrir e ativar

1. Abra o **SAP MCP Manager** pelo atalho ou menu iniciar
2. Clique em **🔐 Não ativada** no topo
3. Cole seu **Subscription ID** (do e-mail do Stripe ou do Portal) OU clique em **💳 Comprar** pra ir pro checkout
4. Após ativação: badge fica verde, botão **⚡ Aplicar ao Claude** libera

---

## Alternativa: instalar via terminal admin (contorna SmartScreen)

Se a sua política corporativa não permite "Executar assim mesmo", peça ao TI:

```powershell
# Abre PowerShell como Administrador e roda:
Unblock-File -Path 'C:\caminho\para\SAPMCPManager-Setup-1.0.6.exe'
Start-Process 'C:\caminho\para\SAPMCPManager-Setup-1.0.6.exe'
```

---

## Por que isso acontece?

O Windows SmartScreen bloqueia instaladores que:
- Não têm certificado EV (Extended Validation) de assinatura de código (>R$1.500/ano)
- OU têm certificado normal mas ainda não acumularam reputação (começa a liberar após algumas centenas de downloads)
- OU são desconhecidos (primeiro download do arquivo)

**Isso não é bug do SAP MCP Manager** — qualquer app novo no mercado passa por isso. Ex: VSCode, Node.js, 7-Zip, e outros também mostraram esse aviso quando lançaram versões novas.

---

## Se não conseguir instalar

- **"Vírus detectado":** antivírus corporativo agressivo. Adicione `SAPMCPManager-Setup-1.0.6.exe` e a pasta `C:\Users\<você>\AppData\Local\Programs\SAP MCP Manager\` na **lista de exceções** do seu antivírus.
- **"Precisa de permissão de administrador":** executar o instalador com "Executar como administrador" (clique direito).
- **Nada funciona:** contato do suporte tem fornecido instaladores assinados em pacote MSIX pra ambientes com restrições.
