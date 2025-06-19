

# Projeto de Redes para Packet Tracer - Empresa "Leandro da Silva Stampini" - 2025

Este repositório contém a documentação e o passo a passo de configuração de uma infraestrutura de rede para uma empresa fictícia, projetada no Cisco Packet Tracer.

## Sumário

1.  [Visão Geral do Projeto](//##1\. Visão Geral do Projeto )
2.  [Estrutura da Empresa e Requisitos](https://www.google.com/search?q=%232-estrutura-da-empresa-e-requisitos)
      * [Departamentos e Localização](https://www.google.com/search?q=%23departamentos-e-localiza%C3%A7%C3%A3o)
      * [Contagem de PCs por Setor](https://www.google.com/search?q=%23contagem-de-pcs-por-setor)
      * [Infraestrutura Física Necessária](https://www.google.com/search?q=%23infraestrutura-f%C3%ADsica-necess%C3%A1ria)
3.  [Planejamento da Infraestrutura Lógica](https://www.google.com/search?q=%233-planejamento-da-infraestrutura-l%C3%B3gica)
      * [Distribuição de Setores por VLANs](https://www.google.com/search?q=%23distribui%C3%A7%C3%A3o-de-setores-por-vlans)
      * [Esquema de Endereçamento IP (com CIDR)](https://www.google.com/search?q=%23esquema-de-endere%C3%A7amento-ip-com-cidr)
      * [Endereçamento IP de Gerenciamento de Roteadores Wireless](https://www.google.com/search?q=%23endere%C3%A7amento-ip-de-gerenciamento-de-roteadores-wireless)
      * [Endereçamento IP de Pool DHCP para Notebooks](https://www.google.com/search?q=%23endere%C3%A7amento-ip-de-pool-dhcp-para-notebooks)
4.  [Guia de Implementação no Cisco Packet Tracer](https://www.google.com/search?q=%234-guia-de-implementa%C3%A7%C3%A3o-no-cisco-packet-tracer)
      * [Ferramentas e Cabos](https://www.google.com/search?q=%23ferramentas-e-cabos)
      * [Passo a Passo da Configuração](https://www.google.com/search?q=%23passo-a-passo-da-configura%C3%A7%C3%A3o)
        1.  [Início e Representação dos Prédios](https://www.google.com/search?q=%231-in%C3%ADcio-e-representa%C3%A7%C3%A3o-dos-pr%C3%A9dios)
        2.  [Adicionando PCs e Servidores](https://www.google.com/search?q=%232-adicionando-pcs-e-servidores)
        3.  [Adicionando Switches e Roteadores Wireless](https://www.google.com/search?q=%233-adicionando-switches-e-roteadores-wireless)
        4.  [Conectando PCs e Servidores aos Switches](https://www.google.com/search?q=%234-conectando-pcs-e-servidores-aos-switches)
        5.  [Conectando Switches de Departamento aos Roteadores Wireless](https://www.google.com/search?q=%235-conectando-switches-de-departamento-aos-roteadores-wireless)
        6.  [Adicionando e Conectando Laptops Wireless](https://www.google.com/search?q=%236-adicionando-e-conectando-laptops-wireless)
        7.  [Substituindo e Configurando o Switch Central DTI (Camada 3)](https://www.google.com/search?q=%237-substituindo-e-configurando-o-switch-central-dti-camada-3)
        8.  [Criando VLANs em Todos os Switches](https://www.google.com/search?q=%238-criando-vlans-em-todos-os-switches)
        9.  [Configurando Portas de Acesso (Access Ports)](https://www.google.com/search?q=%239-configurando-portas-de-acesso-access-ports)
        10. [Configurando Portas Trunk em Todos os Switches](https://www.google.com/search?q=%2310-configurando-portas-trunk-em-todos-os-switches)
        11. [Configurando Endereços IP Fixos em PCs e Servidores](https://www.google.com/search?q=%2311-configurando-endere%C3%A7os-ip-fixos-em-pcs-e-servidores)
        12. [Configurando Roteadores Wireless (APs com DHCP para Notebooks)](https://www.google.com/search?q=%2312-configurando-roteadores-wireless-aps-com-dhcp-para-notebooks)
        13. [Configurando Servidores DNS e HTTP](https://www.google.com/search?q=%2313-configurando-servidores-dns-e-http)
5.  [Testes de Conectividade](https://www.google.com/search?q=%235-testes-de-conectividade)

-----

## 1\. Visão Geral do Projeto

Este projeto visa dimensionar e implementar uma infraestrutura de rede para uma empresa em 2025, utilizando o Cisco Packet Tracer. A rede é distribuída em dois prédios e um departamento de TI central (DTI), com segmentação por VLANs, endereçamento IP otimizado por CIDR, e serviços essenciais como DHCP, DNS e HTTP.

## 2\. Estrutura da Empresa e Requisitos

### Departamentos e Localização

  * **Prédio 1:**
      * **Administração:** Financeiro, Recepção, Vendas.
      * **Desenvolvimento:** Testes, Projetos de Software.
  * **Prédio 2:**
      * **Administração:** Recursos Humanos, Telefonia, Compras.
      * **Desenvolvimento:** Suporte.
  * **DTI (Rede):** Localiza o Switch Central de Camada 3.

### Contagem de PCs por Setor

  * **Financeiro** (Prédio 1): 6 PCs
  * **Recursos Humanos** (Prédio 2): 8 PCs
  * **Recepção** (Prédio 1): 4 PCs
  * **Telefonia** (Prédio 2): 2 PCs
  * **Compras** (Prédio 2): 10 PCs
  * **Vendas** (Prédio 1): 10 PCs
  * **Suporte** (Prédio 2): 18 PCs
  * **Testes** (Prédio 1): 4 PCs
  * **Projetos** (Prédio 1): 16 PCs

### Infraestrutura Física Necessária

  * **Switches:** 1 Switch por agrupamento lógico de Prédio/Departamento (total de 4 Switches de Camada 2: Prédio 1 ADM, Prédio 1 DEV, Prédio 2 ADM, Prédio 2 DEV).
  * **Switch Central DTI:** 1 Switch de Camada 3 (Multilayer Switch) no DTI, atuando como o núcleo de roteamento.
  * **Roteadores Wireless:** 1 Roteador Wireless por agrupamento lógico de Prédio/Departamento (total de 4).
  * **Servidores:** 3 Servidores (HTTP, DNS, DHCP) para **cada** agrupamento lógico de Prédio/Departamento (total de 12 servidores).

## 3\. Planejamento da Infraestrutura Lógica

### Distribuição de Setores por VLANs

  * **VLAN 2:** Financeiro e Compras
  * **VLAN 3:** Recursos Humanos, Recepção, Telefonia e Vendas
  * **VLAN 4:** Projetos e Testes
  * **VLAN 5:** Suporte

### Esquema de Endereçamento IP (com CIDR)

  * **VLAN 1 (Gerenciamento de APs e Default):**
      * Rede: `192.168.1.0/24` (Máscara: `255.255.255.0`)
      * Gateway: `192.168.1.1` (SVI no Switch Central DTI)
      * Uso: IPs fixos para gerenciamento dos Roteadores Wireless.
  * **VLAN 2 (Financeiro e Compras) - IPs Fixos, Classe C:**
      * Rede: `192.168.2.0/27` (Máscara: `255.255.255.224`)
      * Gateway: `192.168.2.1` (SVI no Switch Central DTI)
      * Hosts utilizáveis: `192.168.2.2` a `192.168.2.30`
      * Servidores: Prédio 1 ADM: `.2` (HTTP), `.3` (DNS), `.4` (DHCP). Prédio 2 ADM: `.5` (HTTP), `.6` (DNS), `.7` (DHCP).
      * PCs: Começar a partir de `.8` (Prédio 2 ADM) e `.10` (Prédio 1 ADM) ou IPs disponíveis.
  * **VLAN 3 (RH, Recepção, Telefonia, Vendas) - DHCP, Classe A:**
      * Rede: `10.0.0.0/26` (Máscara: `255.255.255.192`)
      * Gateway: `10.0.0.1` (SVI no Switch Central DTI)
      * Hosts utilizáveis (para DHCP pool): `10.0.0.2` a `10.0.0.62`
      * Servidor DHCP: O Switch Central DTI (Camada 3) atuará como servidor DHCP para esta VLAN.
  * **VLAN 4 (Projetos e Testes) - IPs Fixos, Classe B:**
      * Rede: `172.16.0.0/27` (Máscara: `255.255.255.224`)
      * Gateway: `172.16.0.1` (SVI no Switch Central DTI)
      * Hosts utilizáveis: `172.16.0.2` a `172.16.0.30`
      * Servidores: Prédio 1 DEV: `.2` (HTTP), `.3` (DNS), `.4` (DHCP).
      * PCs: Começar a partir de `.5` ou IPs disponíveis.
  * **VLAN 5 (Suporte) - IPs Fixos, sequencial à VLAN 4, Classe B:**
      * Rede: `172.16.0.32/27` (Máscara: `255.255.255.224`)
      * Gateway: `172.16.0.33` (SVI no Switch Central DTI)
      * Hosts utilizáveis: `172.16.0.34` a `172.16.0.62`
      * Servidores: Prédio 2 DEV: `.34` (HTTP), `.35` (DNS), `.36` (DHCP).
      * PCs: Começar a partir de `.37` ou IPs disponíveis.

### Endereçamento IP de Gerenciamento de Roteadores Wireless

  * AP Prédio 1 ADM: `192.168.1.2`
  * AP Prédio 1 DEV: `192.168.1.3`
  * AP Prédio 2 ADM: `192.168.1.4`
  * AP Prédio 2 DEV: `192.168.1.5`
  * Gateway para todos os APs: `192.168.1.1` (SVI VLAN 1 no Switch Central DTI)
  * DNS para todos os APs: `192.168.2.3` (Servidor DNS Prédio 1 ADM)

### Endereçamento IP de Pool DHCP para Notebooks

  * Rede: `172.16.200.0/24` (Máscara: `255.255.255.0`)
  * Gateway (será o próprio AP):
      * AP Prédio 1 ADM: `172.16.200.254`
      * AP Prédio 1 DEV: `172.16.200.253`
      * AP Prédio 2 ADM: `172.16.200.252`
      * AP Prédio 2 DEV: `172.16.200.251`
  * Pool de IPs para notebooks: Começando em `172.16.200.100` (até `172.16.200.250`).
  * DNS para notebooks: `192.168.2.3` (Servidor DNS Prédio 1 ADM)

## 4\. Guia de Implementação no Cisco Packet Tracer

### Ferramentas e Cabos

  * **Ferramentas:** Select (seta), Delete (X), Add Note (bloco de notas), Draw Rectangle.
  * **Cabo Reto de Cobre (Copper Straight-Through):** Para conectar PCs/Servidores a Switches, e Switches a Roteadores Wireless.
  * **Cabo Crossover de Cobre (Copper Cross-Over):** Para conectar Switches entre si (incluindo DTI aos Switches de Departamento) e Roteador Cisco (se usado) a Switch de Camada 3.

### Passo a Passo da Configuração

#### 1\. Início e Representação dos Prédios

1.  Abra o Cisco Packet Tracer.
2.  Use a ferramenta **"Draw Rectangle"** e **"Add Note"** para desenhar e rotular as áreas: "Prédio 1", "Prédio 2" e "Área de Rede (DTI)".

#### 2\. Adicionando PCs e Servidores

1.  Na categoria **"End Devices"**, adicione os **PCs** e **Servers** conforme a contagem e distribuição por setor. Use a ferramenta "Add Note" para identificar os setores dentro dos prédios.

#### 3\. Adicionando Switches e Roteadores Wireless

1.  Na categoria **"Network Devices"**:
      * **Switches de Departamento (Camada 2):** Adicione 4 switches **`2960 Series`** (ou `2960-48TT` se precisar de mais portas) para cada agrupamento lógico: "Prédio 1 ADM", "Prédio 1 DEV", "Prédio 2 ADM", "Prédio 2 DEV".
      * **Switch Central DTI (Camada 3):** Adicione 1 **`3560-24PS`** ou **`3650`** (Multilayer Switch) na área DTI. **Ligue-o** na aba "Physical" adicionando um `AC-POWER-SUPPLY` e clicando no botão de energia.
      * **Roteadores Wireless:** Adicione 4 **"Wireless Router"** (ex: `Linksys WRT300N`) para cada agrupamento lógico de departamento.

#### 4\. Conectando PCs e Servidores aos Switches

1.  Use o **Cabo Reto de Cobre (Copper Straight-Through)**.
2.  Conecte cada **PC** e **Servidor** ao seu respectivo **Switch de Departamento** (usando portas FastEthernet, ex: `Fa0/1`, `Fa0/2`, etc.). Anote as portas utilizadas para cada setor.

#### 5\. Conectando Switches de Departamento aos Roteadores Wireless

1.  Use o **Cabo Reto de Cobre (Copper Straight-Through)**.
2.  Conecte a porta FastEthernet do **Switch de Departamento** (ex: `Fa0/24`) à porta **LAN** do **Roteador Wireless** correspondente.

#### 6\. Adicionando e Conectando Laptops Wireless

1.  Na categoria **"End Devices"**, adicione os **Laptops**.
2.  **Para cada Laptop:**
      * Clique no Laptop -\> Aba **"Physical"**.
      * **Desligue o Laptop**.
      * Remova o módulo `PT-HOST-NM-1FFE` (placa Ethernet).
      * Adicione o módulo **`WPC300N`** (placa wireless).
      * **Ligue o Laptop**.

#### 7\. Substituindo e Configurando o Switch Central DTI (Camada 3)

1.  **Remova o Switch Central DTI Antigo (se já havia um `2960`)** e adicione o novo **Multilayer Switch** (`3560-24PS` ou similar).
2.  **Reconecte os 4 Switches de Departamento ao Novo Switch Central DTI** usando **Cabos Crossover de Cobre**. Use as portas `GigabitEthernet1/0/1` a `GigabitEthernet1/0/4` (ou as portas GigE reais do seu Switch de Camada 3). Anote qual porta do DTI se conecta a qual Switch de Departamento.
3.  **No Novo "Switch Central DTI" (Camada 3) - CLI:**
    ```
    enable
    configure terminal
    # Re-crie as VLANs
    vlan 2
    name FINANCEIRO_COMPRAS
    exit
    vlan 3
    name RH_RECEPCAO_TELEFONIA_VENDAS
    exit
    vlan 4
    name PROJETOS_TESTES
    exit
    vlan 5
    name SUPORTE
    exit
    # Re-configure as Portas TRUNK para os Switches de Departamento (use as portas GigE que você conectou)
    interface range GigabitEthernet1/0/1 - 4  # Adapte o range
    shutdown
    switchport mode trunk
    switchport trunk native vlan 1
    switchport trunk allowed vlan 1,2,3,4,5
    description Links_to_Department_Switches
    no shutdown
    exit
    # Crie as Interfaces Virtuais de Switch (SVIs) - Os Gateways para Cada VLAN
    ip routing # Habilita o roteamento de IP globalmente
    interface vlan 1
    ip address 192.168.1.1 255.255.255.0
    no shutdown
    exit
    interface vlan 2
    ip address 192.168.2.1 255.255.255.224
    no shutdown
    exit
    interface vlan 3
    ip address 10.0.0.1 255.255.255.192
    no shutdown
    exit
    interface vlan 4
    ip address 172.16.0.1 255.255.255.224
    no shutdown
    exit
    interface vlan 5
    ip address 172.16.0.33 255.255.255.224
    no shutdown
    exit
    # Configure DHCP no Switch de Camada 3 (para a VLAN 3)
    ip dhcp excluded-address 10.0.0.1 10.0.0.9
    ip dhcp pool VLAN3_POOL
    network 10.0.0.0 255.255.255.192
    default-router 10.0.0.1
    dns-server 192.168.2.3 # Servidor DNS do Prédio 1 ADM (VLAN 2)
    exit
    end
    copy running-config startup-config
    ```

#### 8\. Criando VLANs em Todos os Switches

1.  Para **CADA UM dos 4 Switches de Departamento** ("Prédio 1 ADM", "Prédio 1 DEV", "Prédio 2 ADM", "Prédio 2 DEV") e no **Novo "Switch Central DTI"**:
    ```
    enable
    configure terminal
    vlan 2
    name FINANCEIRO_COMPRAS
    exit
    vlan 3
    name RH_RECEPCAO_TELEFONIA_VENDAS
    exit
    vlan 4
    name PROJETOS_TESTES
    exit
    vlan 5
    name SUPORTE
    exit
    end
    copy running-config startup-config
    ```

#### 9\. Configurando Portas de Acesso (Access Ports)

1.  Para **CADA UM dos 4 Switches de Departamento**:
      * **Identifique as portas conectadas a PCs/Servidores de cada setor.**
      * **No "Switch Prédio 1 ADM" - CLI:**
        ```
        enable
        configure terminal
        # Financeiro (VLAN 2)
        interface range FastEthernet0/1 - 6 # Adapte as portas
        switchport mode access
        switchport access vlan 2
        description PCs_Financeiro
        exit
        # Recepção (VLAN 3)
        interface range FastEthernet0/7 - 10 # Adapte as portas
        switchport mode access
        switchport access vlan 3
        description PCs_Recepcao
        exit
        # Vendas (VLAN 3)
        interface range FastEthernet0/11 - 20 # Adapte as portas
        switchport mode access
        switchport access vlan 3
        description PCs_Vendas
        exit
        # Servidores Financeiro (VLAN 2)
        interface range FastEthernet0/21 - 23 # Adapte as portas
        switchport mode access
        switchport access vlan 2
        description Servidores_Financeiro
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 1 DEV" - CLI:**
        ```
        enable
        configure terminal
        # Testes (VLAN 4)
        interface range FastEthernet0/1 - 4 # Adapte as portas
        switchport mode access
        switchport access vlan 4
        description PCs_Testes
        exit
        # Projetos (VLAN 4)
        interface range FastEthernet0/5 - 20 # Adapte as portas
        switchport mode access
        switchport access vlan 4
        description PCs_Projetos
        exit
        # Servidores Projetos (VLAN 4)
        interface range FastEthernet0/21 - 23 # Adapte as portas
        switchport mode access
        switchport access vlan 4
        description Servidores_Projetos
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 2 ADM" - CLI:**
        ```
        enable
        configure terminal
        # Telefonia (VLAN 3)
        interface range FastEthernet0/1 - 2 # Adapte as portas
        switchport mode access
        switchport access vlan 3
        description PCs_Telefonia
        exit
        # Recursos Humanos (VLAN 3)
        interface range FastEthernet0/3 - 10 # Adapte as portas
        switchport mode access
        switchport access vlan 3
        description PCs_Servers_RH
        exit
        # Compras (VLAN 2)
        interface range FastEthernet0/11 - 20 # Adapte as portas
        switchport mode access
        switchport access vlan 2
        description PCs_Servers_Compras
        exit
        # Servidores Compras (VLAN 2)
        interface range FastEthernet0/21 - 23 # Adapte as portas
        switchport mode access
        switchport access vlan 2
        description Servidores_Compras
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 2 DEV" - CLI:**
        ```
        enable
        configure terminal
        # Suporte (VLAN 5)
        interface range FastEthernet0/1 - 21 # Adapte as portas (PCs e Servidores)
        switchport mode access
        switchport access vlan 5
        description PCs_Servers_Suporte
        exit
        end
        copy running-config startup-config
        ```

#### 10\. Configurando Portas Trunk em Todos os Switches

1.  Para **CADA UM dos 4 Switches de Departamento** (Fa0/1 para Wireless e porta GigE/FaE para DTI):
      * **No "Switch Prédio 1 ADM" - CLI:**
        ```
        enable
        configure terminal
        interface FastEthernet0/24 # Porta para Router Wireless
        switchport mode trunk
        switchport trunk allowed vlan 1,2,3
        description Link_to_Router_Wireless_P1_ADM
        exit
        interface GigabitEthernet0/1 # Porta para DTI
        switchport mode trunk
        switchport trunk native vlan 1
        switchport trunk allowed vlan 1,2,3,4,5
        description Link_to_Switch_Central_DTI
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 1 DEV" - CLI:**
        ```
        enable
        configure terminal
        interface FastEthernet0/24 # Porta para Router Wireless
        switchport mode trunk
        switchport allowed vlan 1,4
        description Link_to_Router_Wireless_P1_DEV
        exit
        interface GigabitEthernet0/1 # Porta para DTI
        switchport mode trunk
        switchport trunk native vlan 1
        switchport allowed vlan 1,2,3,4,5
        description Link_to_Switch_Central_DTI
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 2 ADM" - CLI:**
        ```
        enable
        configure terminal
        interface FastEthernet0/24 # Porta para Router Wireless
        switchport mode trunk
        switchport allowed vlan 1,2,3
        description Link_to_Router_Wireless_P2_ADM
        exit
        interface GigabitEthernet0/1 # Porta para DTI
        switchport mode trunk
        switchport trunk native vlan 1
        switchport allowed vlan 1,2,3,4,5
        description Link_to_Switch_Central_DTI
        exit
        end
        copy running-config startup-config
        ```
      * **No "Switch Prédio 2 DEV" - CLI:**
        ```
        enable
        configure terminal
        interface FastEthernet0/22 # Porta para Router Wireless
        switchport mode trunk
        switchport allowed vlan 1,3,5
        description Link_to_Router_Wireless_P2_DEV
        exit
        interface FastEthernet0/23 # Porta para DTI
        switchport mode trunk
        switchport trunk native vlan 1
        switchport allowed vlan 1,2,3,4,5
        description Link_to_Switch_Central_DTI
        exit
        end
        copy running-config startup-config
        ```

#### 11\. Configurando Endereços IP Fixos em PCs e Servidores

  * **Servidores (VLANs 2, 4, 5):** Configure em **"Desktop" -\> "IP Configuration"** como `Static`.
      * Prédio 1 ADM (VLAN 2): HTTP `192.168.2.2`, DNS `192.168.2.3`, DHCP `192.168.2.4`. Gateway: `192.168.2.1`. DNS: `192.168.2.3`.
      * Prédio 2 ADM (VLAN 2): HTTP `192.168.2.5`, DNS `192.168.2.6`, DHCP `192.168.2.7`. Gateway: `192.168.2.1`. DNS: `192.168.2.3`.
      * Prédio 1 DEV (VLAN 4): HTTP `172.16.0.2`, DNS `172.16.0.3`, DHCP `172.16.0.4`. Gateway: `172.16.0.1`. DNS: `172.16.0.3`.
      * Prédio 2 DEV (VLAN 5): HTTP `172.16.0.34`, DNS `172.16.0.35`, DHCP `172.16.0.36`. Gateway: `172.16.0.33`. DNS: `172.16.0.35`.
  * **PCs (VLANs 2, 4, 5):** Configure em **"Desktop" -\> "IP Configuration"** como `Static`.
      * **VLAN 2 (Financeiro/Compras):** IPs de `192.168.2.8` em diante. Máscara: `255.255.255.224`. Gateway: `192.168.2.1`. DNS: `192.168.2.3`.
      * **VLAN 4 (Projetos/Testes):** IPs de `172.16.0.5` em diante. Máscara: `255.255.255.224`. Gateway: `172.16.0.1`. DNS: `172.16.0.3`.
      * **VLAN 5 (Suporte):** IPs de `172.16.0.37` em diante. Máscara: `255.255.255.224`. Gateway: `172.16.0.33`. DNS: `172.16.0.35`.
  * **PCs (VLAN 3):** Configure em **"Desktop" -\> "IP Configuration"** como **`DHCP`**. Eles receberão IPs do Switch Central DTI.

#### 12\. Configurando Roteadores Wireless (APs com DHCP para Notebooks)

1.  Para **CADA UM dos 4 Roteadores Wireless**:
      * Acesse a **"GUI"**.
      * **Basic Setup:**
          * **Router IP (IP de gerenciamento do AP, VLAN 1):**
              * AP Prédio 1 ADM: `192.168.1.2`
              * AP Prédio 1 DEV: `192.168.1.3`
              * AP Prédio 2 ADM: `192.168.1.4`
              * AP Prédio 2 DEV: `192.168.1.5`
              * **Subnet Mask:** `255.255.255.0`
              * **Default Gateway:** `192.168.1.1` (SVI da VLAN 1 no Switch DTI)
              * **Static DNS 1:** `192.168.2.3` (Servidor DNS principal)
          * **DHCP Server:** `Enabled`.
          * **Start IP Address:** `172.16.200.100`.
          * **Maximum number of Users:** `50`.
          * **Static DNS 1:** `192.168.2.3`.
      * **Wireless -\> Basic Wireless Settings:**
          * **SSID:** Ex: `ADM_PR1_WIFI`.
          * **SSID Broadcast:** `Disabled`.
      * **Wireless -\> Wireless Security:**
          * **Security Mode:** `WPA2 Personal`.
          * **Passphrase:** `cisco123`.
      * Clique em `Save Settings`.
2.  **Laptops (Notebooks):** Configure em **"Desktop" -\> "IP Configuration"** como **`DHCP`**.

#### 13\. Configurando Servidores DNS e HTTP

1.  **Servidor DNS (Prédio 1 ADM - IP: `192.168.2.3`):**
      * Clique no servidor -\> **"Services" -\> "DNS"**.
      * **DNS Service:** `On`.
      * **Adicionar Registros DNS:**
          * **Name:** `[seunome].com` / **Type:** `A Record` / **Address:** `192.168.2.2` (Servidor HTTP P1 ADM)
          * **Name:** `desenvolvimento.com` / **Type:** `A Record` / **Address:** `172.16.0.2` (Servidor HTTP P1 DEV)
          * **Name:** `suporte.com` / **Type:** `A Record` / **Address:** `172.16.0.34` (Servidor HTTP P2 DEV)
          * **Name:** `compras.com` / **Type:** `A Record` / **Address:** `192.168.2.5` (Servidor HTTP P2 ADM)
          * Clique em `Add` após cada registro.
2.  **Servidores HTTP (Páginas Web):**
      * Para **CADA UM dos 4 Servidores HTTP**:
          * Clique no servidor -\> **"Services" -\> "HTTP"**.
          * **HTTP Service:** `On`.
          * Edite a página `index.html` com uma mensagem personalizada. Clique em `Save`.

## 5\. Testes de Conectividade

Após toda a configuração, realize os seguintes testes para validar a rede:

1.  **Testar DHCP:** Verifique se os PCs da VLAN 3 e os Laptops obtiveram IPs e configurações de gateway/DNS corretos.
2.  **Ping dentro da mesma VLAN:** De um PC para outro PC/Servidor na mesma VLAN.
3.  **Ping entre VLANs:** De um PC na VLAN X para um PC/Servidor na VLAN Y.
4.  **Ping para Gateways:** De um PC para a SVI da sua VLAN no Switch Central DTI.
5.  **Ping para o Servidor DNS:** De qualquer PC para o IP do Servidor DNS principal (`192.168.2.3`).
6.  **Acessar Páginas Web por Domínio:** De qualquer PC, abra o "Web Browser" e digite os domínios configurados (`seunome.com`, `desenvolvimento.com`, etc.).

-----

Este `README.md` completo deve servir como um guia abrangente para a sua implementação e um excelente registro para o GitHub\!
