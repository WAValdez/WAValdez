<div align="center">

<!-- ================= HEADER ================= -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=8B0000&height=175&section=header&text=WINDER%20VALDEZ&fontSize=42&fontColor=ffffff&fontAlignY=35&desc=Spider-Sec%20%7C%20IT%20Infrastructure%20%26%20Defensive%20Engineering&descAlignY=58&descAlign=50" width="100%" />

<br>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=19&pause=1000&color=DC2626&center=true&vCenter=true&repeat=true&width=760&lines=Spider-Sense+Active%3A+Vulnerability+Management+%26+Hardening;Windows+Server+%2B+GPO+%2B+Credential+Guard;Centralized+Patching+(WSUS)+%26+L2+Network+Defense;Turning+Exposed+Attack+Surfaces+into+Resilient+Systems)](https://git.io/typing-svg)

<br>

> *"Un gran acceso conlleva una gran responsabilidad."*  
> **Enfoque dual:** Estabilidad operativa de **TI** + Reducción rigurosa de riesgo en **Ciberseguridad**.

<br>

![Windows Server](https://img.shields.io/badge/Windows_Server-Hardening_%26_GPO-1E3A8A?style=for-the-badge&logo=windows&logoColor=white)
![Nessus](https://img.shields.io/badge/Vulnerability_Mgmt-Nessus-8B0000?style=for-the-badge&logo=shield-alt&logoColor=white)
![WSUS](https://img.shields.io/badge/Patch_Control-WSUS-111827?style=for-the-badge)
![Network](https://img.shields.io/badge/Network_Security-L2_AP_%26_WPA2--AES-991B1B?style=for-the-badge)

</div>

---

## 🕸️ Spider-Bio: ¿Por qué TI + Ciberseguridad en un mismo perfil?

La mayoría de los perfiles se quedan en un extremo: **administran sistemas sin pensar en el atacante** o **reportan vulnerabilidades sin entender cómo opera una red en producción**. Yo trabajo justo en el punto donde ambos mundos chocan:

* 🕷️ **Detección con criterio (Nessus):** No se trata de exportar PDFs gigantes, sino de identificar exposiciones reales, priorizar según riesgo y validar que la remediación cerró el problema.
* 🛡️ **Endurecimiento real de hosts:** Implementación de **Credential Guard** para aislar secretos en memoria, restricción de almacenamiento extraíble por **GPO** y *hardening* de **Windows Server**.
* 📦 **Control de cambios y parches:** Gestión centralizada mediante **WSUS** para mantener los sistemas actualizados con orden, minimizando ventanas de exposición e interrupciones operativas.
* 📡 **Defensa en Capa 2 y perímetro local:** Reutilización y *hardening* de una **ONT Huawei HG8546M** como **AP en Capa 2**, mitigación de conflictos **IPv4** y migración de cifrado débil **TKIP** hacia **WPA2-AES**.

---

## 🗺️ Arquitectura Operativa & Defensa (Spider-Grid)

```mermaid
flowchart TB
    classDef spiderRed fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#ffffff;
    classDef itBlue fill:#1e3a8a,stroke:#60a5fa,stroke-width:2px,color:#ffffff;
    classDef darkSec fill:#111827,stroke:#dc2626,stroke-width:2px,color:#f9fafb;
    classDef auditBox fill:#31102f,stroke:#f43f5e,stroke-width:2px,color:#ffffff;

    subgraph PERIMETER["🌐 CAPA PERIMETRAL Y RED LOCAL (L2 / WI-FI)"]
        AP["📡 ONT Huawei HG8546M en Modo AP (Capa 2)<br/>Eliminación de TKIP → WPA2-AES<br/>Control y prevención de conflictos IPv4"]:::spiderRed
    end

    subgraph INFRA["🖥️ CAPA DE INFRAESTRUCTURA Y HARDENING"]
        WSUS["📦 WSUS Server<br/>Distribución Controlada de Parches"]:::itBlue
        WINS["🛡️ Windows Server Hardened<br/>Credential Guard · Políticas GPO<br/>Control de Almacenamiento Extraíble"]:::itBlue
    end

    subgraph ASSURANCE["🕷️ SENTIDO ARÁCNIDO: AUDITORÍA Y CUMPLIMIENTO"]
        NESSUS["🎯 Nessus Vulnerability Management<br/>Escaneo · Priorización · Verificación Post-Hardening"]:::auditBox
    end

    AP -->|"Tráfico Segmentado / Capa 2"| WINS
    WSUS -->|"Despliegue Controlado de Actualizaciones"| WINS
    NESSUS -.->|"1. Detección de Exposiciones"| WINS
    NESSUS -.->|"2. Evaluación de Red y Hosts"| AP
    WINS -.->|"3. Remediación Aplicada"| NESSUS
