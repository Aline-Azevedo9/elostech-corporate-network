# ElosTech Corporate Network (VLANs + Segurança)

Projeto de laboratório com foco em infraestrutura de redes e fundamentos de cibersegurança, simulando uma rede corporativa segmentada com VLANs, Router-on-a-Stick e controles de segurança.

---

## 🎯 Objetivo
Construir uma rede corporativa organizada e segura, separando os setores por VLAN e garantindo isolamento do ambiente de visitantes.

---

## 🧩 Cenário
- VLAN 10 – Administração  
- VLAN 20 – Financeiro  
- VLAN 30 – Visitantes (isolada)

---

## 🛠️ Tecnologias e Ferramentas
- Cisco Packet Tracer  
- Switch Cisco  
- Router Cisco  
- Ubuntu Server  
- VLAN, Trunk, Router-on-a-Stick  
- DHCP  
- ACL

---

## 🗺️ Topologia

![Topologia](imgs/topologia.png)

---

## 📌 Implementação (Resumo)
1. Criação das VLANs no switch  
2. Configuração de portas de acesso  
3. Configuração de trunk entre switch e roteador  
4. Criação de subinterfaces no roteador  
5. Configuração de DHCP no Ubuntu Server  
6. Testes de conectividade  
7. Aplicação de ACL para isolamento da VLAN 30  

---

## 🔐 Segurança
- Segmentação por VLAN  
- Isolamento da rede de visitantes  
- Controle de tráfego com ACL  

---

## 🧠 Aprendizados
- Segmentação de redes na prática  
- Inter-VLAN Routing  
- Importância da documentação  
- Fundamentos de segurança em redes  

---

## 🧪 Evidências (Comandos e Resultados)

### VLANs configuradas
```bash
Switch# show vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/1, Fa0/2
10   ADMINISTRACAO                    active    Fa0/3, Fa0/4
20   FINANCEIRO                       active    Fa0/5, Fa0/6
30   VISITANTES                       active    Fa0/7, Fa0/8

### Trunk entre Switch e Roteador
Switch# show interfaces trunk

Port        Mode         Encapsulation  Status        Native vlan
Fa0/24      on           802.1q         trunking      1

Vlans allowed on trunk
10,20,30

### Subinterfaces no Roteador
Router# show ip interface brief

Interface              IP-Address      OK? Method Status                Protocol
Gig0/0.10              192.168.10.1    YES manual up                    up
Gig0/0.20              192.168.20.1    YES manual up                    up
Gig0/0.30              192.168.30.1    YES manual up                    up

### Teste de Conectividade
PC-ADM> ping 192.168.10.1
Reply from 192.168.10.1: bytes=32 time<1ms TTL=255

PC-ADM> ping 192.168.20.10
Reply from 192.168.20.10: bytes=32 time<1ms TTL=255

PC-VISITANTES> ping 192.168.10.10
Request timed out.

---

## 👩‍💻 Autora
Aline Azevedo  
Infraestrutura de Redes | Cybersegurança | SOC (em formação)
