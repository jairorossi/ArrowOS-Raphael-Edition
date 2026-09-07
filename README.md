# ArrowOS 12.1 — Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)

[![Android Version](https://img.shields.io/badge/Android-12.1%20%2812L%29-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://arrowos.net)
[![Device](https://img.shields.io/badge/Device-Xiaomi%20Mi%209T%20Pro%20%2F%20Redmi%20K20%20Pro-FF6900?style=for-the-badge&logo=xiaomi&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Build Status](https://img.shields.io/badge/Build-Passed-brightgreen?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Play Integrity](https://img.shields.io/badge/Play%20Integrity-MEETS_DEVICE_INTEGRITY%20%2F%20STRONG-blue?style=for-the-badge&logo=googleplay&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)

Custom ROM não-oficial de alta estabilidade e performance baseada no **ArrowOS 12.1 (Android 12L)** para o **Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)**, compilada com GApps nativos integrados e suporte a 100% de integridade e apps bancários.

---

## 📦 Detalhes do Release

- **Versão da ROM:** ArrowOS 12.1 (Android 12L / `arrow-12.1`)
- **Variante:** GAPPS (MindTheGapps Oficial Integrado)
- **Arquivo:** `Arrow-v12.1-raphael-UNOFFICIAL-20260907-GAPPS.zip`
- **Tamanho:** `1.3 GB`
- **SHA256:** `973f3ca2aef2c1f79acb2543d2348edbfa92731bdd4abcafdd5a55f1d87289b0`
- **Link de Download Direto:** [Gofile - Download ArrowOS 12.1](https://gofile.io/d/VRjGxmSU)

---

## ✨ Destaques e Otimizações

- 🚀 **Performance Extrema:** Compilado com LLVM/Clang otimizado para o SoC Qualcomm Snapdragon 855 (`-march=armv8.2-a -mcpu=cortex-a76`).
- 🔋 **PowerHAL AIDL Nativo:** Gerenciamento dinâmico de bateria e performance via `power-libperfmgr` com `powerhint.json` ajustado para o Raphael.
- 🛡️ **Play Integrity & Banking:** Patch em `AttestationHooks.java` no framework base para aprovação automática no Play Protect / Device Integrity (Google Pay, Nubank, Itaú, Inter, Mercado Pago funcionam out-of-the-box).
- 📸 **Câmera & Pop-Up Motor:** Suporte completo à câmera retrátil pop-up (com efeitos sonoros/LED nativos) e motor HAL (`vendor.xiaomi.hardware.motor`).
- 🎨 **Material You:** Suporte ao themer monet com paleta de cores dinâmica e personalização leve do ArrowOS.
- 📶 **Conectividade:** VoLTE, VoWiFi, Bluetooth Audio LDAC/aptX-HD e Wi-Fi 5GHz 100% funcionais.

---

## 📲 Guia de Instalação

### Pré-requisitos:
1. Bootloader desbloqueado.
2. Custom Recovery instalado ([OrangeFox Recovery](https://orangefox.download) ou [TWRP](https://twrp.me/xiaomi/xiaomimi9tpro.html)).
3. Firmware compatível: **MIUI V12.5.2.0.RFKMIXM / Global** (ou superior).

### Passo a Passo:
1. Reinicie em modo Recovery (`Power + Volume +`).
2. Faça backup dos seus dados essenciais.
3. Vá em **Wipe** e faça `Format Data` (digite `yes`).
4. Conecte o aparelho ao PC ou use OTG e copie o ZIP da ROM:
   - `Arrow-v12.1-raphael-UNOFFICIAL-20260907-GAPPS.zip`
5. Selecione o arquivo no Recovery e confirme a instalação (**Flash**).
6. Após a conclusão, reinicie o sistema (**Reboot System**).
7. Aproveite o ArrowOS 12.1!

---

## 🛠️ Instruções de Compilação (Build from Source)

```bash
# 1. Inicialize a source tree do ArrowOS 12.1
repo init -u https://github.com/ArrowOS/android_manifest.git -b arrow-12.1 --depth=1

# 2. Configure os manifests locais para as árvores do Raphael
mkdir -p .repo/local_manifests
curl -sL https://raw.githubusercontent.com/jairorossi/ArrowOS-Raphael-Edition/main/.repo/local_manifests/raphael.xml -o .repo/local_manifests/raphael.xml

# 3. Sincronize os repositórios
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j8

# 4. Prepare as variáveis de ambiente e inicie a compilação com GApps
source build/envsetup.sh
export ARROW_GAPPS=true
lunch arrow_raphael-userdebug
make bacon -j8
```

---

## 📜 Créditos & Agradecimentos

- [ArrowOS Team](https://arrowos.net)
- [LineageOS Project](https://lineageos.org)
- [TheMuppets](https://gitlab.com/the-muppets) (Vendor Blobs)
- Equipe de desenvolvimento Raphael / SM8150
