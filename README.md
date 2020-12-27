# Fontoraw  
**Font to raw**  
  
**Fontoraw** began its life as a tool to batch edit characters on 8 bit computer fonts but it can be used for any kind of bitmap to bytes conversion.  
You save a `.png` font dump, edit it on a graphic program and use **Fontoraw** to generate an output file to read back or paste on the target computer.  
You can format the output file on a variety of ways to better suit your needs.  
  
>**Fontoraw** needs the [Pillow library](https://pillow.readthedocs.io/en/stable/).  

**Input example:**  
<img src="Example.png" alt="Example PNG" width="400">  
  
**Some output examples:**  
  
Assembly:  
  
	decb 0x78,0xfc,0xcc,0xcc,0xcc,0xfc,0x78,0x00,0x70,0xf0,0xf0,0x30,0x30,0xfc,0xfc,0x00  
	decb 0x78,0xfc,0xcc,0x1c,0x38,0xfc,0xfc,0x00,0x78,0xfc,0xcc,0x18,0xcc,0xfc,0x78,0x00  
  
Basic:  
  
	10 data 120,252,204,204,204,252,120,0  
	20 data 112,240,240,48,48,252,252,0  
  
Binary:  
  
	01111000  
	11111100  
  
**You must enter the parameters on the code itself:**  
  
- `png_file = ''`  
The `.png` file to load.  
  
- `out_file = ''`  
The output file. A text file or a hex dump, depending on the data format.  
  
- `out_type = 0`  
Where to output the data:  
If `hex dump` is chosen as the data format the output will be binary otherwise a text file will be exported.  
`0` Screen and file.  
`1` Screen.  
`2` File.  
  
- `data_form = 0`  
The data format:  
`0` Decimal.  
`1` Hexadecimal.  
`2` Binary.  
`3` Hex dump.  
  
- `char_w = 0`  
The width of each character.  
  
- `char_h = 0`  
The height of each character.  
  
- `srt_char = 0`  
The first character to convert.  
The first character is `1`  
  
- `end_char = 0`  
The last character to convert.  
  
- `txt_pref = ''`  
The text at the start of each line.  
ie. `decb`  
  
- `data_pref = ''`  
A prefix for each byte.  
ie. `0x`  
  
- `data_sep = ''`  
A separator for the bytes.  
ie. `,`  
  
- `data_pad = 0`  
If the bytes are padded with `0`s:  
`0` Not padded.  
`1` Padded.  
  
- `data_batch = 0`  
The amount of bytes on each line.  
  
- `line_gap = 0`  
Insert a blank line after this many lines.  
  
- `line_srt = 0`  
Start a number count to go at the start if the line.  
(Useful for Basic)  
  
- `line_inc = 0`  
The line number increment.  
`0` For no line numbering.  
  
- `byte_pad = 0`  
Pad bytes with less than 8 bits:  
`0` In front.  
`1` At the end.  
  
- `luma_tresh = 0`  
`0` to `255`  
The pixel luminance to turn to white.  
All else will be black.  
  
- `verbose = 2`  
The amount of feedback given:  
`0` None  
`1` Errors  
`2` All  
