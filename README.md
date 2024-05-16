# Documentación Mejorada por Z0SO

## Instalación

Para comenzar, instala el paquete utilizando el gestor de paquetes correspondiente a tu distribución. Si estás utilizando Arch Linux, ejecuta el siguiente comando en tu terminal:

```bash 
sudo pacman -S fastfetch 
```

Una vez instalado, simplemente ejecuta el siguiente comando en tu terminal:

```bash
fastfetch
```

## Uso

Aquí te mostramos algunas formas comunes de utilizar Fastfetch:

- **Ejecutar con configuración predeterminada:**
```bash
fastfetch
```

- **Ejecutar con todos los módulos compatibles para encontrar lo que necesitas:**
```bash
fastfetch -c all.jsonc
```

- **Mostrar todos los datos detectados por Fastfetch en formato JSON:**
```bash
fastfetch -s <modulo> --format json
```

- **Mostrar mensajes de ayuda:**
```bash
fastfetch --help
```

- **Generar el archivo de configuración basado en los argumentos de línea de comandos:**
```bash
fastfetch --arg1 --arg2 --gen-config
```

# Personalización

*Fastfetch* ofrece una amplia capacidad de personalización a través de JSONC (JSON con comentarios) para su configuración. Puedes ajustar la estructura del texto y el logotipo según tus preferencias.

## Estructura del Texto

Puedes explorar los archivos de configuración predefinidos en la carpeta [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets) para obtener ejemplos útiles sobre cómo ajustar los argumentos de formato. Una vez que hayas encontrado el estilo que te guste, puedes copiar el código y pegarlo en tu archivo de configuración `config.jsonc`. Si aún no tienes un archivo de configuración, puedes generar uno ejecutando:

```bash
fastfetch --gen-config  
```

El archivo de configuración generado se encontrará en `/home/<usuario>/.config/fastfetch/config.jsonc`.

## Personalización del Logotipo

Los logotipos también son altamente personalizables. Consulta la [documentación del logotipo](https://github.com/fastfetch-cli/fastfetch/wiki/Logo-options) para obtener más información sobre cómo ajustarlos.

### Ejemplo

Aquí te proporciono un fragmento de código para configurar un logotipo para *Arch Linux*. Debes reemplazar `<nombre-de-tu-imagen>.png` con el nombre de tu imagen png y asegurarte de que esté ubicada en la carpeta `~/.config/fastfetch/img/`. El código sería así:

```jsonc
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "logo": {
        "source": "$(ls ~/.config/fastfetch/img/<nombre-de-tu-imagen>.png | shuf -n 1)",
        "width": 32,
        "height": 16,
        "padding": {
            "top": 4,
            "left": 2
        }
    }
```

Puedes ajustar los valores de `width`, `height`, `padding`, y las posiciones según tus preferencias.

*¡Experimenta y personaliza tu experiencia con Fastfetch según tus gustos y necesidades!*

