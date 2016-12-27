### NMS Batch MBIN Processor

This tool allows you to batch extract, decrypt, edit, and repackage files for the game No Man's Sky using MBINCompiler and PSARC.

#### How to use it

* Extract the archive into a directory.
* Place NMSARC.515F1D3.pak, or any other PAK files you want to experiment with from your PCBANKS directory, in the directory you extracted the archive to.
* Open cmd.exe/Powershell and run "node.exe --max_old_space_size=16192 bmp.js".
  * If you plan on extracting multiple PAK files, and don't use the BAT file, you will need to increase the RAM limit for NodeJS with the max_old_space_size flag. I suggest 16192MB if you plan to extract all the files.
* After it runs, it will create a MOD PAK file that you can place in your MODS directory.

The config file is Settings.ini. Inside the brackets [], the script will search the decompiled MBIN XML files for a Filename property.

The format:
[TemplateName:PropertyToTarget]
ChildPropertyName=ChildPropertyValue

It will then apply the settings you specify inside its parent block provided the keys preceding the "=" exist.

#### Available options

  * --mt - Enable multi-threading of MBINCompiler
  * --xml - Skip decompilation and update existing XML files
  * -h, --help - Display this information