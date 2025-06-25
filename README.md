✅ **Passo a Passo: Implantação de Máquina Virtual no Azure**

---

### 1. Criar um Resource Group (Grupo de Recursos)

Acesse o portal do Azure: https://portal.azure.com

Na barra de pesquisa, digite **Resource Group** e clique em **Create**.

**Preencha:**
- **Subscription (Assinatura):** selecione a sua.
- **Resource Group name:** exemplo `az104-rg8`.
- **Region:** escolha uma região próxima dos seus usuários ou exigida pelo projeto (ex: Brazil South).
- **Tags:** (Opcional) adicione para organização.

**Finalize:** Vá para a aba **Review + Create** e clique em **Create**.

---

### 2. Criar a Máquina Virtual

No portal, pesquise por **Virtual Machine** e clique em **Create > Azure virtual machine**.

**Na aba Basics, preencha:**
- **Subscription:** mesma usada no Resource Group.
- **Resource group:** selecione `az104-rg8`.
- **Virtual machine name:** exemplo `az104-vm1`.
- **Region:** mesma do resource group.
- **Availability Zone:** selecione 1 (ou 1 e 2 se zona redundante).
- **Image:** ex: Windows Server 2022 ou Ubuntu 20.04 LTS.
- **Size:** ex: Standard B1s para testes.
- **Admin username:** escolha um nome.
- **Password:** digite e confirme.
- **Inbound ports:** `None` para segurança ou `Allow selected ports` para RDP/SSH.

---

### 3. Outras Configurações

- **Disks:** deixe como padrão (geralmente Premium SSD).
- **Networking:** padrão para teste; para produção, configure VNet e NSG.
- **Management:** habilite **Boot diagnostics** se desejar monitoramento da inicialização.
- **Advanced, Tags:** opcionais.

---

### 4. Revisar e Criar

- Vá até a aba **Review + create**.
- O Azure validará as configurações.
- Clique em **Create** para iniciar a implantação.

---

### 5. Redimensionar a Máquina Virtual (Resize)

- Após a criação da VM `az104-vm1`, clique na máquina.
- Acesse o menu lateral e clique em **Size (Tamanho)**.
- Será exibido o tamanho atual da VM e uma lista de opções disponíveis.
- Escolha o novo tamanho (ex: o primeiro da lista) e clique em **Resize**.

⚠️ **Atenção:** Se a VM estiver ligada, será reiniciada automaticamente para aplicar o novo tamanho.

---

### 6. Gerenciar Discos da Máquina Virtual

- No menu lateral da VM `az104-vm1`, clique em **Disks**.

Você verá duas opções principais:
- 🔴 **Attach an existing disk:** Vincular um disco que já foi criado anteriormente.
- 🟢 **Create and attach a new disk:** Criar e anexar um novo disco à VM.

Ao criar um novo disco, selecione o **Storage type** desejado. Exemplo: `Standard HDD` (mais econômico).

---

### ✅ Passo a Passo: Desanexando um Disco da Máquina Virtual

- Na aba **Disks** da sua VM `az104-vm1`, localize a lista de discos anexados.
- Clique no ícone de **ejetar** (parece um cabo sendo desconectado) ao lado do disco a ser removido.
- Confirme a ação.

⚠️ **Importante:**
- O disco **não será excluído**, apenas **desanexado** da VM.
- Ele pode ser **reutilizado** em outras VMs.
- Certifique-se de que o disco **não está em uso**, para evitar perda de dados não salvos.
