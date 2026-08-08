# Laboratorio de cifrado GPG en entorno Kali Linux

Práctica realizada dentro del módulo **MF0489_3 – Criptografía y Comunicaciones Seguras**, del certificado de profesionalidad **IFCT0109 – Seguridad Informática (Nivel 3, SEPE)**, cursado en CEINA (abr. 2026 – jul. 2026).

## Objetivo

Implementar un flujo completo de cifrado asimétrico con GPG (GNU Privacy Guard) para garantizar la confidencialidad, integridad y autenticidad de la información en un entorno de comunicaciones seguras, trabajando sobre una máquina virtual Kali Linux desplegada con VMware.

## Entorno

- **Hipervisor:** VMware Workstation
- **Sistema operativo:** Kali Linux
- **Herramienta principal:** GnuPG (GPG)

## Qué se ha hecho

1. **Generación de par de claves** (pública/privada) con `gpg --full-generate-key`.
2. **Intercambio de claves públicas** para establecer un canal de confianza.
3. **Cifrado y descifrado de ficheros** con `gpg --encrypt` / `gpg --decrypt`.
4. **Firma digital** de ficheros (`gpg --sign`) y verificación (`gpg --verify`).
5. **Gestión del keyring**: importación, exportación y revocación de claves.

## Comandos clave utilizados

```bash
# Generar par de claves
gpg --full-generate-key

# Listar claves disponibles
gpg --list-keys
gpg --list-secret-keys

# Exportar clave pública
gpg --export -a "nombre_usuario" > clave_publica.asc

# Importar clave pública de otro usuario
gpg --import clave_publica.asc

# Cifrar un fichero para un destinatario
gpg --encrypt --recipient "nombre_destinatario" fichero.txt

# Descifrar un fichero recibido
gpg --decrypt fichero.txt.gpg > fichero_descifrado.txt

# Firmar un fichero
gpg --sign fichero.txt

# Verificar una firma
gpg --verify fichero.txt.gpg
```

## Conceptos aplicados

- Criptografía asimétrica (par de claves pública/privada)
- Confidencialidad, integridad y autenticidad de la información
- Web of trust / gestión de confianza entre claves
- Buenas prácticas en comunicaciones seguras

---
**Autor:** Bernat Marcet Claramunt
**Contexto:** Práctica formativa — IFCT0109, CEINA
