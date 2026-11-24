<div align="center">

# 🕷️ WINDER VALDEZ
### **Spider-Sec & IT Infrastructure Engineer**
`Vulnerability Management` · `Windows Server & GPO Hardening` · `WSUS Patching` · `L2 / Wi-Fi Security`

> *"Un gran acceso conlleva una gran responsabilidad."*  
> **Estabilidad operativa de TI + Reducción rigurosa de superficie de ataque en Ciberseguridad.**

[![Hardening](https://img.shields.io/badge/Windows_Hardening-Credential_Guard_%26_GPO-1E3A8A?style=for-the-badge&logo=windows&logoColor=white)](#repositorios-principales)
[![Vuln Mgmt](https://img.shields.io/badge/Vulnerability_Mgmt-Nessus-8B0000?style=for-the-badge&logo=shield-alt&logoColor=white)](#repositorios-principales)
[![Patching](https://img.shields.io/badge/Patch_Control-WSUS-111827?style=for-the-badge)](#repositorios-principales)
[![Network](https://img.shields.io/badge/Network_Sec-L2_AP_%26_WPA2--AES-991B1B?style=for-the-badge)](#repositorios-principales)

</div>

---

## 🕸️ Spider-Bio: Enfoque Operativo y Defensivo

Muchos perfiles separan la **administración de TI** de la **ciberseguridad**. En la práctica, la seguridad real ocurre cuando quien endurece un sistema o configura una red entiende el impacto operativo, la continuidad del negocio y el comportamiento de un atacante.

* 🎯 **Gestión de Vulnerabilidades (Nessus):** Identificación de exposiciones, priorización por riesgo, aplicación de *hardening* y verificación de cumplimiento.
* 🛡️ **Endurecimiento de Sistemas (Windows Server & GPO):** Aislamiento de credenciales con **Credential Guard**, control de dispositivos de almacenamiento extraíble por **GPO** y refuerzo de configuraciones críticas.
* 📦 **Control de Parches (WSUS):** Distribución centralizada y controlada de actualizaciones de seguridad para reducir ventanas de exposición sin comprometer la estabilidad.
* 📡 **Seguridad de Red Local y Capa 2:** Reutilización y *hardening* de una **ONT Huawei HG8546M** como **AP en Capa 2**, mitigación de conflictos **IPv4** y migración de cifrado débil **TKIP** hacia **WPA2-AES**.

---

## 🗺️ Arquitectura de Defensa y Control (Spider-Grid)

```mermaid
flowchart LR
    classDef red fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#ffffff;
    classDef sys fill:#1e3a8a,stroke:#60a5fa,stroke-width:2px,color:#ffffff;
    classDef sec fill:#18181b,stroke:#f43f5e,stroke-width:2px,color:#ffffff;

    subgraph EDGE["🌐 Red Local y Perímetro"]
        AP["📡 ONT Huawei HG8546M<br/>Modo AP Capa 2 · WPA2-AES<br/>Control IPv4 (Sin TKIP)"]:::red
    end

    subgraph CORE["🖥️ Infraestructura y Hardening"]
        WSUS["📦 WSUS<br/>Parches Controlados"]:::sys
        WIN["🛡️ Windows Server Hardened<br/>Credential Guard · GPO · USB Control"]:::sys
    end

    subgraph AUDIT["🕷️ Verificación y Riesgo"]
        NESSUS["🎯 Nessus<br/>Detección · Remediación · Cumplimiento"]:::sec
    end

    EDGE -->|"Tráfico Segmentado"| CORE
    WSUS -->|"Actualizaciones"| WIN
    NESSUS -.->|"Escaneo y Validación"| CORE
    NESSUS -.->|"Evaluación de Exposición"| EDGE
