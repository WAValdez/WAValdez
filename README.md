<div align="center">

# 🕷️ Winder Valdez
### **IT Infrastructure & Cybersecurity | Vulnerability Management · Hardening · Network Defense**

*"Un gran acceso conlleva una gran responsabilidad."*  
**Detectando exposiciones antes de que se conviertan en incidentes · Blindando sistemas críticos**

[![Vulnerability Mgmt](https://img.shields.io/badge/Vulnerability_Mgmt-Nessus-8B0000?style=for-the-badge&logo=shield-alt&logoColor=white)](#repositorios-destacados-spider-labs)
[![Windows Hardening](https://img.shields.io/badge/Hardening-Windows_Server_%26_GPO-1E3A8A?style=for-the-badge&logo=windows&logoColor=white)](#repositorios-destacados-spider-labs)
[![Patch Mgmt](https://img.shields.io/badge/Patch_Mgmt-WSUS-0F172A?style=for-the-badge)](#repositorios-destacados-spider-labs)
[![Network Sec](https://img.shields.io/badge/Network_Sec-L2_AP_%26_WPA2--AES-DC2626?style=for-the-badge)](#repositorios-destacados-spider-labs)

</div>

---

## 🕸️ Sentido Arácnido Operativo (Sobre mí)

A los líderes de **TI** les importa la **estabilidad, continuidad y control**; a los de **Ciberseguridad** les importa la **reducción de superficie de ataque, visibilidad y remediación real**. Mi trabajo vive exactamente en esa intersección.

En lugar de quedarme en teoría, construyo y documento laboratorios enfocados en cómo se protege una red en la vida real: **identificar fallos con criterio, endurecer endpoints y servidores, controlar parches y asegurar la capa de red** sin romper la operación.

- 🎯 **Gestión de Vulnerabilidades:** Escaneo, priorización y validación de remediación con **Nessus**, cerrando brechas de forma medible.
- 🛡️ **Hardening de Sistemas:** Mitigación de robo de credenciales mediante **Credential Guard**, control de medios extraíbles por **GPO** y endurecimiento de **Windows Server**.
- 🔄 **Control de Parches & Red:** Despliegue estructurado vía **WSUS** y *hardening* de infraestructura local (conversión de **ONT Huawei HG8546M a AP en Capa 2**, prevención de conflictos **IPv4** y migración de cifrado débil **TKIP** hacia **WPA2-AES**).

---

## 🗺️ Topología de Defensa & Operación (Spider-Grid)

```mermaid
flowchart LR
    subgraph Perimeter["🌐 Perímetro & Red Local (L2 / Wi-Fi)"]
        ONT["ONT Huawei HG8546M<br/>Modo AP Capa 2 · WPA2-AES<br/>Control IPv4 (Sin TKIP)"]
    end

    subgraph Core["🖥️ Infraestructura & Hardening"]
        WSUS["WSUS Server<br/>Distribución Controlada de Parches"]
        WIN["Windows Server Hardened<br/>Credential Guard · Políticas GPO<br/>Control USB / Almacenamiento"]
    end

    subgraph Assurance["🕷️ Sentido Arácnido: Auditoría & Cumplimiento"]
        NESSUS["Nessus Scanner<br/>Detección · Priorización · Verificación"]
    end

    Perimeter --> Core
    NESSUS -. "Escaneo & Validación" .-> Core
    NESSUS -. "Evaluación de Exposición" .-> Perimeter
    WSUS -. "Parches de Seguridad" .-> WIN
