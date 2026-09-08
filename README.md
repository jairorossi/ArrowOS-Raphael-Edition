# 🏹 ArrowOS 12.1 — Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)

[![Android Version](https://img.shields.io/badge/Android-12.1%20%2812L%29-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://arrowos.net)
[![Device](https://img.shields.io/badge/Device-Xiaomi%20Mi%209T%20Pro%20%2F%20Redmi%20K20%20Pro-FF6900?style=for-the-badge&logo=xiaomi&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Build Status](https://img.shields.io/badge/Build-Passed-brightgreen?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Play Integrity](https://img.shields.io/badge/Play%20Integrity-MEETS_DEVICE_INTEGRITY%20%2F%20STRONG-blue?style=for-the-badge&logo=googleplay&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)

Custom ROM não-oficial de alta estabilidade, bateria impecável e desempenho baseada no **ArrowOS 12.1 (Android 12L)** para o **Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)**, com **GApps integrados**, **Play Integrity aprovado nativamente** e arquitetura oficial de **Partições Dinâmicas Retrofit (6.0 GB Super Pool)**.

---

## 📦 Downloads e Detalhes da Versão

| Arquivo | Descrição | Link de Download |
| :--- | :--- | :--- |
| 🏹 **ROM ArrowOS 12.1 GAPPS** | Build completa oficial com GApps, Kernel 4.14 e Play Integrity | **[Baixar no Gofile (1.28 GB)](https://gofile.io/d/Hjqco7BN)** |
| 🦊 **OrangeFox Recovery R11.3** | Recovery Oficial Unified com suporte a Dynamic Partitions | [Baixar no Gofile](https://gofile.io/d/ViAUVw29) |
| 🔄 **Script Retrofit Dynamic** | Conversor de partições 1-click para compatibilidade total | [Baixar no Gofile](https://gofile.io/d/xHIgmhrp) |
| 📶 **Firmware MIUI 12.5.2** | Firmware Oficial MIUI Global Android 11 para Raphael | [Baixar no Gofile](https://gofile.io/d/iMakeCes) |

### 🔐 Integridade do Arquivo da ROM:
- **Nome:** `Arrow-v12.1-raphael-UNOFFICIAL-20260908-GAPPS.zip`
- **Tamanho:** `1.342.842.750 bytes` (~1.28 GB)
- **SHA-256:** `ac78321938233ca0ce4d25f06cb00ac97aae6a5529441077ef4520c9394ef1ab`

---

## ✨ Principais Destaques Desta Edição

1. 🚀 **Kernel Oficial Qualcomm SM8150 (4.14):**
   - Árvore de kernel completa (`raphael_defconfig`) compilada com Clang 12 e `LLVM_IAS=1`.
   - Kernel compactado em `Image.gz` (16 MB) e DTBs completos de 1.8 MB com todos os drivers do Raphael.
2. 🛡️ **Play Integrity / Banking Fix Nativo:**
   - Patch `AttestationHooks.java` no framework base para aprovação em apps bancários (Google Pay, Nubank, Itaú, Bradesco, Inter, Mercado Pago).
3. 📸 **Câmera Pop-Up & Motor Xiaomi:**
   - Suporte completo ao motor retrátil da câmera frontal (`vendor.xiaomi.hardware.motor`), incluindo LEDs de acionamento e efeitos sonoros customizáveis.
4. 🟢 **Leitor Biométrico Sob a Tela (FOD Goodix):**
   - Resposta instantânea e precisa no leitor óptico sob a tela.
5. 🔋 **PowerHAL AIDL & VINTF Compliance:**
   - Compatibilidade total com a especificação VINTF do Android 12L para gerenciamento dinâmico de performance e economia de energia.

---

## 📲 Guia Completo de Instalação (OrangeFox / TWRP)

### Passo 1: Preparar o Recovery e Partições
1. Reinicie no **OrangeFox Recovery** (ou TWRP).
2. Se estiver vindo de uma ROM antiga sem partições dinâmicas, vá em **Install** e instale o [Script Retrofit Dynamic](https://gofile.io/d/xHIgmhrp).
3. Vá em **Wipe > Advanced Wipe** e selecione:
   - `Dalvik / ART Cache`, `Cache`, `Data`, `Metadata`.
4. Arraste para confirmar a limpeza.
5. Vá no menu principal > **Reboot > Recovery** (⚠️ **Importante reiniciar o Recovery antes de continuar!**).

### Passo 2: Instalar Firmware e ROM
1. Ao reiniciar o Recovery, vá em **Install**.
2. Instale o [Firmware MIUI 12.5.2 Global](https://gofile.io/d/iMakeCes) (se ainda não estiver instalado).
3. Instale o arquivo da **ROM ArrowOS 12.1 GAPPS**:
   - `Arrow-v12.1-raphael-UNOFFICIAL-20260908-GAPPS.zip`.

### Passo 3: Format Data e Inicialização
1. Vá em **Wipe > Format Data**.
2. Digite `yes` e confirme no botão verde.
3. Toque em **Reboot System**!

---

## 📂 Árvores e Repositórios no GitHub

- 📱 [Device Tree Raphael](https://github.com/jairorossi/android_device_xiaomi_raphael/tree/arrow-12.1)
- ⚙️ [Common Tree SM8150](https://github.com/jairorossi/android_device_xiaomi_sm8150-common/tree/arrow-12.1)
- 🧠 [Kernel Source](https://github.com/jairorossi/android_kernel_xiaomi_sm8150/tree/lineage-19.1)
- 🏹 [ArrowOS Project](https://github.com/ArrowOS)
