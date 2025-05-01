# Pronunza: Demo de TTS Galego con ONNX (Modelo Celtia)

Caderno de Colab para demostración de síntese de voz (TTS) en galego usando o modelo ONNX de Celtia.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gas/pronunza-tts-galego-onnx-colab/blob/main/Caderno_Colab_TTS_Galego_con_ONNX.ipynb)

## Descrición

Este caderno demostra como usar un modelo VITS pre-adestrado en formato ONNX para xerar voz en galego a partir de texto. Utiliza o modelo `Jarbas/proxectonos-celtia-vits-graphemes-onnx` dispoñible en [Hugging Face](https://huggingface.co/Jarbas/proxectonos-celtia-vits-graphemes-onnx), que é unha conversión do modelo [`Nos_TTS-celtia-vits-graphemes`](https://huggingface.co/proxectonos/Nos_TTS-celtia-vits-graphemes) do Proxecto Nós.

Unha das vantaxes de usar esta versión ONNX co código proporcionado neste caderno é que **non require a instalación nin o uso do software externo Cotovía** para o preprocesamento do texto. A normalización necesaria realízase mediante clases Python incluídas no propio caderno, simplificando a configuración.

Podes escoitar un exemplo da voz xerada aquí:

https://github.com/user-attachments/assets/b8a190c4-ac6f-4148-82b2-e43de3f6d694


## Obxectivo
Facilitar o uso e a experimentación con modelos TTS para galego, proporcionando un exemplo funcional e auto-contido en Google Colab.

## Como Usar

1.  **Abrir en Colab:** Fai clic no botón "Open In Colab" arriba.
2.  **Configurar Directorio (Opcional):** Na cela "1. Configuración...", activa `USE_GDRIVE` e axusta `GDRIVE_PROJECT_PATH` se queres usar Google Drive para gardar os modelos e os audios xerados. Se non, usará o almacenamento temporal de Colab.
3.  **Executar Celas:** Executa as celas en orde (Menú: `Entorno de ejecución` -> `Ejecutar todas`, ou unha por unha).
4.  **Autenticar en Hugging Face:** Introduce o teu token de acceso de Hugging Face (con permisos de lectura) cando se solicite na cela "3. Autenticación...". Asegúrate tamén de ter aceptado os termos de uso na páxina do modelo en Hugging Face.
5.  **Sintetizar Texto:** Na cela "7. Execución...", modifica o `texto_para_sintetizar` se queres probar outras frases e/ou o `nome_base_arquivo`.
6.  **Escoitar/Descargar Audio:** O audio (wav) xérase na carpeta `wavs` (no directorio base elixido) e móstrase un reprodutor ao final da cela
7.  Podes descargar o arquivo desde o panel de arquivos de Colab.

## Dependencias Principais

* `onnxruntime`
* `numpy`
* `scipy`
* `huggingface_hub`
* `requests`

## Modelo Utilizado

* **Modelo:** `Jarbas/proxectonos-celtia-vits-graphemes-onnx` ([Hugging Face](https://huggingface.co/Jarbas/proxectonos-celtia-vits-graphemes-onnx))
* **Orixe:** Conversión ONNX realizada por JarbasAl do modelo `proxectonos/Nos_TTS-celtia-vits-graphemes` ([Hugging Face](https://huggingface.co/proxectonos/Nos_TTS-celtia-vits-graphemes)) do Proxecto [Nós-TTS](https://tts.nos.gal)
* **Licenza do Modelo:** Apache 2.0 (segundo os repositorios de orixe).

## Licenza do Caderno

Este caderno distribúese baixo a **Licenza MIT**. Consulta o arquivo `LICENSE` para máis detalles.

## Agradecementos

* **Proxecto Nós (USC):** Pola creación dos modelos TTS orixinais para galego.
* **JarbasAl (Jarbas):** Pola conversión dos modelos a formato ONNX e por compartilos.
* **Grupo de Tecnoloxías Multimedia (GTM) da UVigo e CRPIH:** Pola creación dos datasets de voz galegos fundamentais.
* **Hugging Face:** Polo aloxamento de modelos e datasets.
* **Google Colab:** Polo contorno de execución gratuíto.
* **Gemini:** Pola asistencia durante o desenvolvemento e depuración deste caderno.

## Limitacións e Traballo Futuro

* A calidade da síntese pode variar segundo a complexidade do texto de entrada.
* Este caderno utiliza unha voz estándar (Celtia). O soporte para diferentes **variantes dialectais ('falas')** requiriría outro tipo de traballos, como o afinamento (fine-tuning) de modelos usando datasets como FalAI (GTM-UVigo) e a disposición pública de versións dixitalizadas de invaluables recursos da lingua como o volume III do Atlas Lingüístico Galego adicado a fonética ([Atlas Lingüístico Galego. Volume III: Fonética](https://ilg.usc.gal/es/publicacions/libros/atlas-linguistico-galego-volume-iii-fonetica)).
