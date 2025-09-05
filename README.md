# create dtb.img/dtbo.img for AOSP
This Tool for create dtb.img and dtbo.img image files.
use help:
```
./mkdtimg <command>

    commands:
      help, dump, create, cfg_create

  ./mkdtimg help all
  ./mkdtimg help <command>

    commands:
      help, dump, create, cfg_create

  ./mkdtimg dump <image_file> (<option>...)

    options:
      -o, --output <filename>  Output file name.
                               Default is output to stdout.
      -b, --dtb <filename>     Dump dtb/dtbo files from image.
                               Will output to <filename>.0, <filename>.1, etc.

  ./mkdtimg create <image_file> (<global_option>...) (<dtb_file> (<entry_option>...) ...)

    global_options:
      --dt_type=<type>         Device Tree type (dtb|acpi). Default: dtb
      --page_size=<number>     Output page size. Default: 2048
      --version=<version>      DTBO version. Default: 0
      --id=<number|path>       The default value to set property id in dt_table_entry. Default: 0
      --rev=<number|path>
      --custom0=<number|path>
      --custom1=<number|path>
      --custom2=<number|path>
      --custom3=<number|path>

      The value could be a number or a DT node path.
      <number> could be a 32-bits digit or hex value, ex. 68000, 0x6800.
      <path> format is <full_node_path>:<property_name>, ex. /board/:id,
      will read the value in given FTB file with the path.

  ./mkdtimg cfg_create <image_file> <config_file> (<option>...)

    options:
      -d, --dtb-dir            The path to load dtb files.
                               Default is load from the current path.
```
# How to Build

## Clone this repositories
```
git clone https://github.com/Mxiier/mkdtimg.git
```
## Compile 
```
make
```
