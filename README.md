# SSII_Repository

# CAI-1 

Este proyecto se centra en la evaluación de contraseñas y la seguridad de claves HMAC, utilizando herramientas como Hashcat y otras técnicas para realizar auditorías y pruebas de seguridad.

## Consultas Realizadas

### Consulta 1: Evaluación de Contraseñas

#### Herramientas utilizadas:
- **Hashcat**: Para realizar ataques de fuerza bruta y diccionario.
- **RockYou**: Lista de contraseñas comúnmente usadas para realizar ataques de diccionario.
- **Have I Been Pwned**: Para verificar si las contraseñas han sido expuestas en bases de datos comprometidas.

### Consulta 2: Seguridad de Claves HMAC

#### Herramientas utilizadas:
- **Hashcat**: Para realizar ataques de fuerza bruta a las claves HMAC-SHA256 y evaluar su fortaleza frente a distintos tiempos de descifrado.

## Scripts y Comandos

A continuación se incluyen los comandos utilizados en los análisis.

### Evaluación de Contraseñas
Para realizar ataques de fuerza bruta y diccionario utilizando Hashcat, puedes ejecutar los siguientes comandos:
- **hashcat -m 1410 hashes.txt fechas.txt --force**

###Conversión Base64 a Hexadecimal python
import base64 
hash_base64 = "hashCode"  # Añadir el hash correspondiente
hash_bytes = base64.b64decode(hash_base64) 
hash_hex = hash_bytes.hex() 
print(hash_hex)

### Generación de Diccionario de Fechas Comunes python
from datetime import datetime, timedelta 
start_date = datetime(1980, 1, 1) 
end_date = datetime(2025, 12, 31) 
formatos = ["%d%m%Y", "%Y%m%d", "%d-%m-%Y", "%d/%m/%Y", "%d%m%y"] 
fechas_generadas = [] 
current_date = start_date 
while current_date <= end_date: 
    for formato in formatos: 
        fechas_generadas.append(current_date.strftime(formato)) 
    current_date += timedelta(days=1) 

with open('fechas.txt', 'w') as file:
    for fecha in fechas_generadas:
        file.write(fecha + '\n')
