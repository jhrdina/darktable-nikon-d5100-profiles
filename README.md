# NIKON D5100: Base-curves, LUTs and input color profiles for Darktable

__Trying to edit RAW photos in Darktable taken with D5100 camera but not satisfied with the default starting point?__

Are you experiencing one of the following symptoms?

 - You're having trouble to restore details in highlights, the whole L channel feels weird, you spend ages on tone-curve corrections
 - Colors are shifted, skin-tones look weird, the default images tend to have a weird color tint (e.g. green)
 - Subtle hue-differences are hard to distinguish

__Yes? Then search no more!__

## Contents

- __`basecurves` folder:__ Basecurve created using `dt-curve-tool` and custom input images with wide dynamic range
    - Run script `2018-01-27_install.sh` from command line to install the basecurve preset
    - It becomes available as `NIKON D5100 2018-01-27 BC` in the basecurve module presets list

- __`luts` folder:__ LUT profiles for this camera created using IT8 color chart and `darktable-chart`
    - Open Darktable, in the right pane in 'styles' section click 'import' and choose a `.dtstyle` file
    - Use them together with basecurve above
    - `D5100 with BC to match JPEG.dtstyle`
        - JPEG - __created to match JPEG file processed by camera__
        - BC - during creation, custom base-curve was applied
        - _works best for me_
    - `D5100 - L96, WB, BC - exact.dtstyle`
        - exact - __created to match reference values from the IT8 color-chart manufacturer__
        - L96 - during creation, exposure of the input files was adjusted to make the white square L channel 96
        - WB - during creation, white-balance was fixed in the input file
        - BC - during creation, custom base-curve was applied
- __`presets` folder:__ Initial profiles I use as a starting point when editing
    - `2018-10-26 D5100 Ultimate Starter`
        - __Basecurve:__ `NIKON D5100 2018-01-27 BC`
        - __LUT and input color profile:__ `D5100 with BC to match JPEG`
        - __Sharpen:__ A little bit more than Darktable default
        - __Shadows and Highlights:__ Disabled, but preset to _bilateral filter_ and not to influence shadows
        - __Split toning:__ Disabled, but preset to more warm colors
        - __Vignetting:__ Disabled, but preset to not to influence saturation

## How to create these on your own

### Basecurve profiling

- No need for special equipment
- [Tutorial on Darktable Blog](https://www.darktable.org/2013/10/about-basecurves/)
- [README of dt-curve-tool](https://github.com/darktable-org/darktable/tree/master/tools/basecurve)

### LUT profiling using IT8 color-checker

- You need to buy an IT8 color-checker with color values files, e.g.
    - X-Rite ColorChecker ($$$ expensive $$$)
    - Affordable alternative: http://targets.coloraid.de/ (you probably want the type C1)
    - Affordable alternative in the Czechia: [BST11 | Centrum FotoŠkoda](https://www.fotoskoda.cz/barevna-tabulka-s-referencnimi-daty-bst11/), see [jhrdina/danes-picta-bst11-cie-cht](https://github.com/jhrdina/danes-picta-bst11-cie-cht) for needed `.cht` and `.cie` files

- [Tutorial by Harry Durgin](https://www.youtube.com/watch?v=11nInNWJHWk)
- [Different one by Shane Milton](https://www.youtube.com/watch?v=GkBgFaSv1kE)