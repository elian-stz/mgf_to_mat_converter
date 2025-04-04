# mgf_to_mat_converter

A Galaxy application to convert MGF file format to MAT.

# Steps taken

The backbone of the XML file was created using this command:

```{bash}
planemo tool_init -i mgf2mat -n mgf2mat --autopygen src/converter.py --tool tool.xml
```

It created the XML file using argparse arguments. However, this XML file was not able to run a Galaxy app since other elements were missing

The following steps consisted in editing the XML file to having a functional application.

The command tag was modified to run the script using the recommended keywords.

The input tag was modified to remove the arguments that were not needed (input and output file format) to get only 3 arguments (MS type, output file name, and input file(s))

The output tag was added since it was previously empty. I added the MGF file, which is counted as a TXT file.

I added the tests tag to assess the ability to correctly convert the file format by using `planemo test`.

# Finality

I was able to wrap the script with Galaxy. While it seems to run, I could not see the output of the script for some reason using the GUI so I don't really know if the application is fully functional.

As for the tests, they result in a failure. Likely because of a wrong file location.