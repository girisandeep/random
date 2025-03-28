Recently, for attending Web Summit, Vancouver, I needed to submit the logo of my startup Terno AI in eps format.

I tried using all online tools but it was frustrating and ended up finding good tools on GitHUb instead.

1. Install vtracer

```pip install vtracer```

I found a nice utility [vtracer https://github.com/visioncortex/vtracer] for tracing an image which is better than Adobe Illustrator.

2. Use vtracer PNG/JPG to SVG

Here is the **python** code I wrote to convert the PNGs and JPGs of my logo to .svg format:

  import os
  import vectortrace as vt
  def convertdir(dir):
      for f in os.listdir(dir):
          if f.lower().endswith(".png") or f.lower().endswith(".png"):
              fullname = dir + "/" + f
              outname = fullname + ".svg"
              print(f"'{fullname}' -> '{outname}'")
              vt.convert_image_to_svg_py(fullname, outname)
  
  
  convertdir("/Users/sandeep/Downloads/terno_final_4/Logo/JPG")
  convertdir("/Users/sandeep/Downloads/terno_final_4/Logo/PNG")

3. Install Inkscape

Download and install Inkscape: https://inkscape.org/

4. Convert all images from svg to eps 

I went to into each of my directories containing JPGs and PNGs to convert .svg to .eps. Here is the ```bash``` code:

  cd /Users/sandeep/Downloads/terno_final_4/Logo/JPG
  for i in *.svg
  do
      inkscape -w 300 -h 300 --export-filename=$i.eps $i
  done

5. That's. You would find the ```.eps``` files in the folder.



