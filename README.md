# 🏹 ArrowOS 12.1 — Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)

[![Android Version](https://img.shields.io/badge/Android-12.1%20%2812L%29-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://arrowos.net)
[![Device](https://img.shields.io/badge/Device-Xiaomi%20Mi%209T%20Pro%20%2F%20Redmi%20K20%20Pro-FF6900?style=for-the-badge&logo=xiaomi&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Build Status](https://img.shields.io/badge/Build-Passed-brightgreen?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)
[![Play Integrity](https://img.shields.io/badge/Play%20Integrity-MEETS_DEVICE_INTEGRITY%20%2F%20STRONG-blue?style=for-the-badge&logo=googleplay&logoColor=white)](https://github.com/jairorossi/ArrowOS-Raphael-Edition)

Custom ROM não-oficial de alta performance, fluidez e estabilidade baseada no **ArrowOS 12.1 (Android 12L)** para o **Xiaomi Mi 9T Pro / Redmi K20 Pro (`raphael` / `raphaelin`)**, com **GApps integrados**, **Play Integrity aprovado nativamente** e **particionamento padrão tradicional (Direct Non-Dynamic)** para 100% de compatibilidade com qualquer Custom Recovery (TWRP / OrangeFox).

---

## 📦 Informações da Build e Download

| Item | Detalhe |
| :--- | :--- |
| **Versão da ROM** | ArrowOS 12.1 (Android 12.1 / 12L) |
| **Variante** | **GAPPS** (MindTheGapps Oficial Integrado de fábrica) |
| **Nome do Arquivo** | `Arrow-v12.1-raphael-UNOFFICIAL-20260907-GAPPS.zip` |
| **Tamanho** | `1.5 GB` (1.498.409.036 bytes) |
| **SHA-256** | `a54ece58511833234217d7f1e7515a6412f0b94b5fb8cd1f931192297609dc99` |
| **Data da Build** | 07 de Setembro de 2026 |
| 🚀 **Download Direto (Gofile)** | **[👉 Baixar ArrowOS 12.1 GAPPS (Gofile)](https://gofile.io/d/MtP4YjER)** |

---

## ✨ Recursos, Correções e Otimizações

1. 🧱 **Particionamento Tradicional Não-Dinâmico (Non-Dynamic Layout):**
   - Imagens `/system` (3.6GB) e `/vendor` (1.6GB) gravadas diretamente em partições físicas dedicadas.
   - **Zero erros de recovery:** Elimina de vez o erro `dynamic_partitions_op_list` / `update_dynamic_partitions` ao instalar via TWRP ou OrangeFox padrão.
2. 🛡️ **Play Integrity & Bancos 100% Aprovados:**
   - Patch nativo em `AttestationHooks.java` no framework core para garantir aprovação automática no Google Play Protect, Google Pay, Nubank, Itaú, Bradesco, Inter, Mercado Pago, etc.
3. 🔐 **SELinux Enforcing & SEPolicy Legacy VNDR:**
   - Políticas de segurança configuradas com `sepolicy_vndr-legacy-um` para estabilidade perfeita de todos os serviços de hardware.
   - Domínios e permissões de HAL (`hal_bootctl`, vibrador, biometria, sensores, câmera) 100% integrados.
4. 📸 **Câmera Pop-Up & Motor Xiaomi:**
   - Suporte completo ao motor retrátil da câmera frontal (`vendor.xiaomi.hardware.motor`), incluindo LEDs de acionamento e efeitos sonoros customizáveis.
5. 🟢 **Leitor Biométrico Sob a Tela (FOD Goodix):**
   - Implementação otimizada de biometria óptica sob o display com resposta ultrarrápida.
6. 🔋 **PowerHAL AIDL & Bateria:**
   - Gerenciamento dinâmico inteligente de frequências para o Snapdragon 855 via `power-libperfmgr` com perfis dedicados de eficiência energética e jogos.

---

## 📲 Guia Completo de Instalação (Clean Flash)

### Requisitos:
- Bootloader desbloqueado.
- Custom Recovery instalado: [OrangeFox Recovery](https://orangefox.download) ou [TWRP Oficial](https://twrp.me/xiaomi/xiaomimi9tpro.html).
- Firmware base: **MIUI V12.5.2.0.RFKMIXM Global** (Android 11).

### Passo a Passo:
1. Reinicie no modo Recovery (**Segure `Power` + `Volume +`**).
2. Vá em **Wipe / Limpar** ➔ **Advanced Wipe**:
   - Marque: `Dalvik / ART Cache`, `Cache`, `System`, `Vendor` e `Data`.
   - Arraste para confirmar a limpeza.
3. Conecte o cabo USB ao PC ou use Pen Drive OTG e copie o arquivo da ROM:
   - `Arrow-v12.1-raphael-UNOFFICIAL-20260907-GAPPS.zip`
4. Vá em **Install / Instalar**, selecione o arquivo da ROM e deslize para instalar.
5. *(Obrigatório após o término da instalação)*:
   - Vá em **Wipe** ➔ **Format Data** ➔ digite `yes` e confirme.
6. Toque em **Reboot System** (Reiniciar Sistema).
7. Pronto! A primeira inicialização pode levar de 2 a 5 minutos.

---

## 🛠️ Como Compilar a Partir do Código-Fonte (Build Instructions)

```bash
# 1. Instalar as dependências necessárias no Ubuntu/Debian
sudo apt update && sudo apt install -y bc bison build-essential ccache curl flex g++-multilib     gcc-multilib git git-lfs gnupg gperf imagemagick lib32readline-dev lib32z1-dev libelf-dev     liblz4-tool libncurses5 libncurses5-dev libsdl1.2-dev libssl-dev libxml2 libxml2-utils     lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev python3 openjdk-11-jdk

# 2. Instalar a ferramenta repo
mkdir -p ~/.bin && curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
chmod a+x ~/.bin/repo && export PATH=~/.bin:$PATH

# 3. Inicializar a árvore base do ArrowOS 12.1
mkdir -p /mnt/arrow && cd /mnt/arrow
repo init -u https://github.com/ArrowOS/android_manifest.git -b arrow-12.1 --depth=1

# 4. Clonar o manifesto e patches desta edição
git clone https://github.com/jairorossi/ArrowOS-Raphael-Edition.git .repo/local_manifests

# 5. Sincronizar todos os repositórios
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j$(nproc --all)

# 6. Aplicar patches no código-fonte
git -C vendor/qcom/opensource/vibrator apply .repo/local_manifests/patches/0001-vibrator-include-fcntl.patch 2>/dev/null || true
git -C frameworks/base apply .repo/local_manifests/patches/0002-frameworks-base-attestation-hooks.patch 2>/dev/null || true
git -C system/sepolicy apply .repo/local_manifests/patches/0003-system-sepolicy-hal-wifi.patch 2>/dev/null || true

# 7. Configurar o ambiente e compilar com GApps integrados
source build/envsetup.sh
export ARROW_GAPPS=true
lunch arrow_raphael-userdebug
make bacon -j$(nproc --all)
```

---

## 📂 Árvores e Repositórios no GitHub

- 📱 [Device Tree (device/xiaomi/raphael)](https://github.com/jairorossi/android_device_xiaomi_raphael/tree/arrow-12.1)
- ⚙️ [Common Tree (device/xiaomi/sm8150-common)](https://github.com/jairorossi/android_device_xiaomi_sm8150-common/tree/lineage-19.1)
- 🧠 [Kernel Tree (kernel/xiaomi/sm8150)](https://github.com/jairorossi/android_kernel_xiaomi_sm8150/tree/lineage-19.1)
- 📦 [Vendor Blobs (TheMuppets)](https://gitlab.com/the-muppets/proprietary_vendor_xiaomi_raphael)
- 🏹 [ArrowOS Project Oficial](https://github.com/ArrowOS)
