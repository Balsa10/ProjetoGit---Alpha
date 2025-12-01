# 📘 Compilado de Estudos: Infraestrutura, Web e Versionamento

Este resumo consolida os conhecimentos adquiridos sobre o funcionamento da Internet, arquitetura de sistemas web, protocolos de segurança cibernética e gestão de código com Git.

---

## 1. 🌐 Estrutura e Comunicação de Dados

### Fundamentos da Conectividade
- **Internet e Web:** É crucial distinguir a infraestrutura física de interconexão global (Internet) dos serviços de navegação e hipermídia que operam sobre ela (Web).
- **Arquitetura de Troca:** A comunicação digital baseia-se predominantemente no modelo cliente-servidor, onde dados são fragmentados em pacotes e roteados até o destino.
- **Desenho de Rede (Topologias):** A organização física dos cabos e dispositivos pode assumir formas como anel, estrela ou malha, cada uma impactando a tolerância a falhas e a eficiência da transmissão.
- **Espinha Dorsal e Pontos de Troca:**
  - **Backbones:** São as vias de altíssima velocidade que transportam o tráfego intercontinental.
  - **IXPs:** Locais físicos onde diferentes provedores conectam suas redes para trocar dados diretamente, diminuindo custos e latência.

### Tipos de Redes por Abrangência
- **LAN:** Redes restritas a locais específicos (escritórios, residências) com alta velocidade.
- **WAN:** Conexões de longa distância que interligam redes locais separadas geograficamente (países, estados).
- **MAN:** Redes que cobrem o perímetro de uma metrópole ou cidade.
- **PAN:** Conexões de curtíssimo alcance focadas no indivíduo, como Bluetooth e NFC.

---

## 2. 🧩 Endereçamento e Protocolos de Rede

### Identificação e IP
- **Evolução do Protocolo IP:** O esgotamento dos endereços IPv4 impulsionou a adoção do IPv6, que oferece um espaço de endereçamento virtualmente infinito e melhorias nativas de segurança.
- **Visibilidade de IP:**
  - *Público:* O endereço visível externamente na internet.
  - *Privado:* Endereços reservados para uso interno na LAN, não roteáveis na internet pública.
- **CIDR e Sub-redes:** O método moderno de alocação de IPs abandonou as "classes" fixas em favor da notação de sufixo (ex: `/24`), permitindo um ajuste mais flexível do tamanho das redes.

### Tradução de Endereços (NAT)
- **Funcionamento:** Técnica que permite que múltiplos dispositivos em uma rede privada naveguem usando um único IP público fornecido pelo provedor.
- **Implicações:** Embora economize IPs, o NAT complica conexões diretas (P2P) e dificulta a identificação precisa da origem do tráfego interno.

### Ferramentas de Diagnóstico
- **Verificação de Latência (Ping):** Utilitário que mede o tempo de ida e volta (RTT) de um pacote e detecta perdas na transmissão.
- **Rastreamento de Rota (Traceroute):** Mapeia cada roteador (salto) pelo qual a informação passa até chegar ao destino final.

---

## 3. 🚚 Transporte e Roteamento de Dados

### Protocolos de Transporte
- **TCP:** Prioriza a integridade dos dados, estabelecendo uma conexão formal (*handshake*) e garantindo que tudo chegue na ordem correta (usado em Web, E-mail).
- **UDP:** Foca na velocidade, enviando dados sem verificar se chegaram, ideal para transmissões ao vivo e jogos onde a rapidez supera a precisão.

### Gerenciamento de Tráfego e QoS
- **Decisão de Rotas:** Roteadores utilizam protocolos como OSPF (interno) e BGP (entre provedores) para determinar o caminho mais eficiente para os dados.
- **Qualidade de Serviço (QoS):** Mecanismos que classificam e priorizam tipos de tráfego sensíveis a atrasos, como voz sobre IP (VoIP) e videoconferências.
- **Latência:** O atraso na comunicação que impacta diretamente a experiência do usuário em aplicações interativas.

---

## 4. 🏗️ Arquitetura de Aplicações Web

### Sistema de Nomes (DNS)
- **Tradução de Nomes:** Funciona como a lista telefônica da internet, convertendo domínios legíveis (`site.com`) em endereços IP numéricos.
- **Hierarquia e Cache:** O processo envolve consultas escalonadas (Raiz -> TLD -> Autoritativo) e uso intensivo de memória cache para acelerar respostas futuras.

### Modelos de Desenvolvimento
- **Camadas de Software:** Separação tradicional em Apresentação (Frontend), Regras de Negócio (Backend) e Armazenamento (Banco de Dados).
- **Microsserviços:** Abordagem que fragmenta sistemas grandes em serviços pequenos e autônomos, facilitando a escalabilidade e manutenção em oposição aos sistemas monolíticos.
- **APIs REST:** Padrão arquitetural que utiliza os métodos do protocolo HTTP (GET, POST, etc.) para integração entre sistemas.

### Formatos e Autenticação
- **Estruturação de Dados:** O JSON se consolidou como padrão leve para web, enquanto o XML oferece maior rigidez estrutural e o YAML é preferido para arquivos de configuração.
- **OAuth:** Protocolo que permite autorizar o acesso a recursos de um usuário sem compartilhar a senha original (login via terceiros).

---

## 5. 🔒 Segurança da Informação

### Proteção e Criptografia
- **Túneis Seguros (VPN):** Criação de canais criptografados sobre redes públicas, garantindo confidencialidade e acesso remoto a recursos corporativos.
- **HTTPS e TLS:** Evolução do HTTP que criptografa a comunicação ponta-a-ponta, assegurando que os dados não sejam interceptados ou adulterados.
- **Certificação:** Autoridades Certificadoras (CAs) emitem certificados digitais para validar a identidade de servidores web.

### Ameaças Cibernéticas
- **Negação de Serviço (DDoS):** Ataques coordenados que visam exaurir os recursos de um sistema, tirando-o do ar.
- **Malware e Engenharia Social:** Softwares maliciosos (vírus, ransomware) e técnicas de manipulação psicológica (phishing) para roubo de dados.
- **Ameaça Interna:** Riscos provenientes de funcionários, seja por intenção maliciosa ou simples negligência com credenciais.

### Defesa Perimetral
- **Firewalls:** Dispositivos ou softwares que filtram o tráfego de rede baseados em regras predefinidas de bloqueio e permissão.
- **Segurança Wireless:** Proteção de redes Wi-Fi através de criptografia robusta (WPA2/3) e segmentação de usuários.

---

## 6. 🐙 Controle de Versão com Git

### Conceitos Centrais
- **Versionamento:** Sistema para rastrear o histórico de modificações em arquivos, permitindo retornar a estados anteriores.
- **Repositório e Snapshots:** O projeto é armazenado em um repositório, onde cada salvamento (commit) registra uma "foto" estática do estado atual.
- **Áreas de Trabalho:** O fluxo envolve mover arquivos da área de trabalho para a área de preparação (staging) antes da confirmação final.

### Gerenciamento de Fluxo
- **Ramificações (Branches):** Criação de linhas de tempo paralelas para desenvolver recursos sem afetar o código principal.
- **Fusão (Merge):** Ato de reintegrar uma ramificação ao tronco principal, o que pode exigir resolução manual de conflitos de código.
- **Sincronização Remota:** Comandos como `push` e `pull` são usados para alinhar o repositório local com servidores na nuvem (ex: GitHub).