
# HideInfo

**Info Hiding Library**  
A collection of small and elegant information-hiding methods  

[![PyPI](https://img.shields.io/pypi/v/HideInfo)](https://pypi.org/project/HideInfo/)  
[![License](https://img.shields.io/pypi/l/HideInfo.svg)](https://github.com/guofei9987/HideInfo/blob/master/LICENSE)  
![Python](https://img.shields.io/badge/python->=3.5-green.svg)  
![Platform](https://img.shields.io/badge/platform-windows%20|%20linux%20|%20macos-green.svg)  
[![stars](https://img.shields.io/github/stars/guofei9987/HideInfo.svg?style=social)](https://github.com/guofei9987/HideInfo/)  
[![fork](https://img.shields.io/github/forks/guofei9987/HideInfo?style=social)](https://github.com/guofei9987/HideInfo/fork)  
[![Downloads](https://pepy.tech/badge/HideInfo)](https://pepy.tech/project/HideInfo)  

---

| **Algorithm**                                                                                  | **Description**                             |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| [Mirage Tank](https://github.com/guofei9987/HideInfo/blob/main/example/example_mirage_tank.py) | Displays different images under different backgrounds |
| [Convert Data to Image](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_as_img.py) | Stores data as an image                    |
| [Hide Data in Image](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_in_img.py) | Hides data inside an image                 |
| [Image Spatial Watermark](https://github.com/guofei9987/HideInfo/blob/main/example/example_img_watermark.py) | Invisible watermark in image spatial domain |
| [Image Seed](https://github.com/guofei9987/HideInfo/blob/main/example/example_img_seed.py)     | Combines files and images into one          |
| [EXIF Data Hiding](https://github.com/guofei9987/HideInfo/blob/main/example/example_img_exif.py) | Embeds information into an image's EXIF    |
| [Convert Data to Audio](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_as_music.py) | Stores data as audio                       |
| [Hide Data in Audio](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_in_music.py) | Hides data inside audio                    |
| [Echo Watermark](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_in_music.py) | Embeds binary data in audio as echoes      |
| [Convert Data to Text](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_as_txt.py) | Stores data as text                        |
| [Hide Data in Text](https://github.com/guofei9987/HideInfo/blob/main/example/example_hide_in_txt.py) | Hides data within a block of text          |

---

## Installation

```bash
pip install HideInfo
```

---

## Mirage Tank

**Functionality:** Merges two images such that one is visible against a black background and the other against a white background.  

### Features:
- Supports color images.
- Commonly used in scenarios where previews and full-size views display differently due to background color differences (e.g., in mobile browsers).
- Example video: [Bilibili](https://www.bilibili.com/video/BV1DF41117c7/)  
- Code example: [example/example_mirage_tank.py](example/example_mirage_tank.py)

```python
from hide_info import mirage_tank

mirage_tank.mirage_tank('image1.png', 'image2.jpeg', 'output.png')
```

---

## hide_as_img: Convert Data to Image

**Functionality:** Converts files, text, or byte-like data into an image format.  

### Features:
- Uses each pixel's channel to store one byte of data.
- Useful for covert communication or situations where only images can be shared (e.g., on social platforms).
- Supports up to 4GB of data storage.
- Code example: [example_hide_as_img.py](example/example_hide_as_img.py)

```python
from hide_info import hide_as_img

# Encode file into an image
hide_as_img.file_encode(filename='file.zip', img_filename='output_image.png')

# Decode file from the image
hide_as_img.file_decode(filename='decoded_file.zip', img_filename='output_image.png')
```

---

## hide_in_img: Hide Data in Image

**Functionality:** Hides files, text, or byte-like data inside an image using the Least Significant Bit (LSB) algorithm.  

### Features:
- Embedded data retrieval does not require the original image.
- Uses bit manipulation for performance.
- Vulnerable to compression and format conversion.
- Code example: [example_hide_in_img.py](example/example_hide_in_img.py)

```python
from hide_info import hide_in_img

# Encode file into an image
hide_in_img.file_encode(filename='file.zip', img_filename='image.png', img_filename_new='output.png')

# Decode file from the image
hide_in_img.file_decode(filename='decoded_file.zip', img_filename='output.png')
```

---

## img_watermark: Image Spatial Watermarking

**Functionality:** Embeds an invisible watermark in the spatial domain of an image.

### Features:
- Resistant to certain transformations like cropping, scaling, and format conversion.
- Effective for images with large uniform color areas.
- Code example: [example_img_watermark.py](https://github.com/guofei9987/HideInfo/blob/main/example/example_img_watermark.py)

```python
from hide_info import img_watermark

# Embed watermark
img_watermark.file_encode(img_filename="image.png", watermark_filename="watermark.png", img_filename_new="watermarked_image.png")

# Extract watermark
img_watermark.file_decode(img_filename="watermarked_image.png", wm_extract="extracted_watermark.png")
```

---


## img_seed: Image Seeder

Functionality: Connects an image and a file together, saving them as an image (still under development).

- Example: [example/example_img_seed.py](example/example_img_seed.py)

## img_exif: Hiding Information in EXIF

Functionality: Hides information in the EXIF data of an image, enabling covert communication or data transmission.

- Example: [example/example_img_exif.py](example/example_img_exif.py)

## hide_in_music: Embedding Data in Music

Functionality: Embeds a piece of information (file/text/bytes) into a music file.

Example:
- [example_hide_in_music.py](example/example_hide_in_music.py)

```python
from hide_info import hide_in_music

# Embed a file into a music file
hide_in_music.file_encode(filename='file_to_hide.zip', music_filename="music.wav", music_filename_new="hidden_in_music.wav")
# Extract the file from the music file
hide_in_music.file_decode(filename="hidden_file.zip", music_filename="hidden_in_music.wav")
```

## hide_as_music: Converting Data to Sound

Functionality: Converts a piece of information (file/text/bytes) into sound.
Principle: Uses 16 tones to represent quaternary numbers. If each tone lasts 0.05 seconds, 10 bytes can be stored per second of sound.
Use Cases:
    - Data hiding and covert transmission
    - Sending arbitrary data in image-only contexts (e.g., social media).

Details:
- Example: [hide_as_music.py](example/example_hide_as_music.py)

```python
from hide_info import hide_as_music

# Convert a file to sound and save it
hide_as_music.file_encode(filename='file_to_hide2.zip', wav_filename='data_as_sound.wav')
# Convert the sound back to a file
hide_as_music.file_decode(filename='extracted_file.zip', wav_filename='data_as_sound.wav')
```

## echo_watermark: Echo Watermark

Echo watermarking is an audio watermarking technique that embeds information by adding echoes to an audio signal. This leverages human auditory psychology, as our ears are less sensitive to short echo delays, making it possible to embed information without affecting perceived sound quality.

Two key parameters for implementation: echo delay and echo amplitude. The delay determines when the echo occurs, and the amplitude affects its intensity. Information can be encoded by varying these parameters.

For example:
- A short delay might represent bit '0', while a long delay represents bit '1'.
- Echo amplitude could also encode different data bits.

Echo watermarking minimally affects sound quality and is robust to compression and format conversion, making it suitable for copyright protection, content authentication, and covert communication.

```python
from hide_info.echo_watermark import EchoWatermark, get_error_rate
from hide_info import utils

ori_file = "audio.wav"  # Carrier audio
embedded_file = "audio_with_watermark.wav"  # Output file with watermark
wm_str = "Echo watermark algorithm, please star!"  # Watermark message

wm_bits = utils.bytes2bin(wm_str.encode('utf-8'))
len_wm_bits = len(wm_bits)

# Embed watermark
echo_wm = EchoWatermark(pwd=111001)
echo_wm.embed(origin_filename=ori_file, wm_bits=wm_bits, embed_filename=embedded_file)

# Extract watermark
echo_wm = EchoWatermark(pwd=111001)
wm_extract = echo_wm.extract(embed_filename=embedded_file, len_wm_bits=len_wm_bits)

wm_str_extract = utils.bin2bytes(wm_extract).decode('utf-8', errors='replace')
print("Extracted watermark:", wm_str_extract)
# Error rate:
get_error_rate(wm_extract, wm_bits)
```

## hide_in_text: Embedding Data in Text

Functionality: Embeds a piece of information (file/text/bytes) into a text document.

Details:
- Tested on macOS and iOS devices; hidden text appears identical to the original. However, spaces may appear on Windows and some Android devices.
- Example: [hide_in_txt.py](example/example_hide_in_txt.py)

```python
from hide_info import hide_in_txt

# Embed a file into an existing text
hide_in_txt.file_encode(filename='file_to_hide2.zip', text_filename='text_sample.txt', text_filename_new='hidden_in_text.txt')
# Extract the file from the text
hide_in_txt.file_decode(filename='extracted_file.zip', text_filename='hidden_in_text.txt')
```

## hide_as_txt: Storing Data as Text

Functionality: Converts a piece of information (file/text/bytes) into a text document.

Details:
- Uses the base85 algorithm.
- Example: [hide_as_txt.py](example/example_hide_as_txt.py)

```python
from hide_info import hide_as_txt

# Convert a file to text and save it
hide_as_txt.file_encode(filename='file_to_hide.zip', txt_filename='data_as_text.txt')
# Extract the file from the text
hide_as_txt.file_decode(filename='extracted_file.zip', txt_filename='data_as_text.txt')
```

## Other Algorithms

Scaled Hidden Image: Pre-computes which pixels will be used during scaling with the nearest neighbor method, and transforms these pixels into another image.
