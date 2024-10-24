#!/usr/bin/env bash
#
# Este script se encarga de invocar los tres programas que permiten la 
# conversion de un PNG a secuencia de pixeles, se procesan esos pixeles y
# posteriormente se convierte esa secuencia de pixeles a un archivo en formato
# PNG
#
# Autor: John Sanabria - john.sanabria@correounivalle.edu.co
# Fecha: 2024-08-22
#
#
for INPUT_JPG in images*.jpg; do
    # Check if any files matching the pattern exist
    if [ ! -e "$INPUT_JPG" ]; then
        echo "No files matching images*.jpg found."
        exit 1
    fi
    
    # Remove the .jpg extension and create a corresponding .bin file
    TEMP_FILE="${INPUT_JPG%.jpg}.bin"
    
    echo "Processing ${INPUT_JPG}..."
    
    # Convert JPG to binary (modify the script to handle JPG instead of PNG)
    python3 fromPNG2Bin.py "${INPUT_JPG}"
    
    # Process the binary file
    ./main "${TEMP_FILE}"
    
     # Convert the processed binary back to PNG (instead of JPG)
    OUTPUT_PNG="${INPUT_JPG%.jpg}.png"
    python3 fromBin2PNG.py "${TEMP_FILE}.new" "${OUTPUT_PNG}"
    
    echo "Finished processing ${INPUT_JPG}. Output saved as ${OUTPUT_PNG}."
  
done
