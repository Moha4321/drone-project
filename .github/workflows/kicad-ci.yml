name: Export KiCad Schematics

on:
  push:
    paths:
      - 'electrical/kicad_project/*.kicad_sch'

jobs:
  export:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v4

      - name: Set up KiCad CLI
        uses: yaqwsx/KiBot@v2
        with:
          # KiBot container bundles KiCad & CLI tools seamlessly
          config: .kibot/config.yml
          dir: electrical/previews
          schema: electrical/kicad_project/kicad_project.kicad_sch

      - name: Upload Previews
        uses: actions/upload-artifact@v4
        with:
          name: schematic-previews
          path: electrical/previews/