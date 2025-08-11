# 🚀Lua Macros para el SAMP
Este script permite crear y ejecutar macros personalizados dentro del juego GTA San Andreas (SAMP) utilizando MoonLoader.
Los macros se ejecutan en secuencia y pueden incluir acciones automáticas, textos predefinidos, y tiempos de espera.<br>
![](https://i.imgur.com/qzmsrcp.png)<br>
## ✨ Características principales<br>
**🔹 1. Perfiles de macros**
- Crea y guarda diferentes conjuntos de macros.<br>
- Cambia entre perfiles sin necesidad de eliminarlos.<br>
- Ideal para jugadores que juegan en varios servidores con comandos distintos.

**🔹 2. Variables dinámicas**<br>
Estas variables pueden ser usadas en tus macros para insertar información automática y personalizada, facilitando la creación de comandos y mensajes dinámicos.

**🔹 3. Soporte multi-idioma**
- Detecta automáticamente el idioma de Windows.
- Disponible en Español e Inglés.
- Si no detecta ninguno, usa inglés por defecto.

## 📜 Sintaxis de Macros
Puedes combinar las siguientes funciones dentro de un macro para automatizar acciones en el juego.

### (chat) texto
Abre el chat e ingresa el texto especificado sin enviarlo.

Ejemplo:
```
(chat) /arrestar
(1000)
usted queda detenido....
```
💡 Esto abrirá el chat y escribirá /arrestar, quedando listo para que lo envíes manualmente. Y la siguiente línea de macro continuará una vez que cierres el chat o envies el /arrestar.

---
### (tiempo)
Establece un tiempo de espera antes de continuar con el siguiente comando del macro.
El tiempo se expresa en milisegundos.

Ejemplo:
```
(1000)
hola
(1000)
hola 2
💡 Espera 1 segundo antes de ejecutar el siguiente macro.
```
---
### Variables de tu personaje
Puedes insertar información de tu personaje en cualquier parte del macro:
| Código    | Inserta                       |
| --------- | ----------------------------- |
| `(id)`    | ID de tu personaje            |
| `(fname)` | Nombre completo               |
| `(name)`  | Solo el nombre (sin apellido) |
---
### Jugador más cercano
Se reemplaza automáticamente con la información del jugador más cercano a ti:
| Código     | Inserta                       |
| ---------- | ----------------------------- |
| `(cid)`    | ID del jugador                |
| `(cfname)` | Nombre completo               |
| `(cname)`  | Solo el nombre (sin apellido) |
---
### Jugador al que apuntas
Inserta la información del jugador que estás apuntando:
| Código     | Inserta                       |
| ---------- | ----------------------------- |
| `(tid)`    | ID del jugador                |
| `(tfname)` | Nombre completo               |
| `(tname)`  | Solo el nombre (sin apellido) |
---
### 📌 Ejemplo de Macro Completo
```
(chat) /me mira a (cfname) con sospecha
(1000)
(chat) ¿Tienes algo que ocultar, (cfname)?
```
💡 Este macro:
```
Escribe en el chat: /me mira a [nombre jugador más cercano] con sospecha.
Espera 1 segundo.
Escribe en el chat: ¿Tienes algo que ocultar, [nombre jugador más cercano]?.
```
---
## ⚙️ Notas
- Las variables del jugador más cercano no enviarán el comando si no se detecta ningún jugador cercano al presionar la tecla. Lo mismo aplica para las variables al apuntar.
- Puedes mezclar texto normal con variables dinámicas en un mismo comando.
- Los tiempos de espera (tiempo) permiten sincronizar tus macros para que se ejecuten con fluidez.
- El patron (chat) siempre requiere que cierres o envies el comando del chat para continuar con el siguiente macro.
