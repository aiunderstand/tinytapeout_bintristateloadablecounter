![](../../workflows/wokwi/badge.svg)

# Binary Tristate Loadable Counter MOD 4
This IP block simulates a binary synchronous (parallel) MOD-4 counter. Applications are CPU's, PWM signal generators, etc. 

## Features: 
- tri-direction (pause, count up, count down) 
- loadable (use data[3:1], eg. for jump instruction, initialization at boot up) 
- synchronous output(at rising edge) with async (ripple) setup of next count) 
- easy to control, fast and scalable (each 1 bit counter only depends on previous counter)

## Interactive simulation 
https://wokwi.com/projects/341423712597181012

## Video
https://youtu.be/a_5DLUsAf9g

## Images
[![Chip interface made with Mixed Radix Circuit Synthesis tool](https://i.imgur.com/tyMDeKP.png)]() 

[![Gate level implementation overview](https://i.imgur.com/DbY4sNm.png)]()

[![GDS (die) shot](https://i.imgur.com/uEzMofO.png)]()



Go to https://tinytapeout.com for instructions!

# How to change the Wokwi project

Edit the [Makefile](Makefile) and change the WOKWI_PROJECT_ID to match your project.

# What is this about?

This repo is a template you can make a copy of for your own [ASIC](https://www.zerotoasiccourse.com/terminology/asic/) design using [Wokwi](https://wokwi.com/).

When you edit the Makefile to choose a different ID, the [GitHub Action](.github/workflows/wokwi.yaml) will fetch the digital netlist of your design from Wokwi.

The design gets wrapped in some extra logic that builds a 'scan chain'. This is a way to put lots of designs onto one chip and still have access to them all. You can see [all of the technical details here](https://github.com/mattvenn/scan_wrapper).

After that, the action uses the open source ASIC tool called [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/) to build the files needed to fabricate an ASIC.

# What files get made?

When the action is complete, you can [click here](https://github.com/mattvenn/wokwi-verilog-gds-test/actions) to see the latest build of your design. You need to download the zip file and take a look at the contents:

* gds_render.svg - picture of your ASIC design
* gds.html - zoomable picture of your ASIC design
* runs/wokwi/reports/final_summary_report.csv  - CSV file with lots of details about the design
* runs/wokwi/reports/synthesis/1-synthesis.stat.rpt.strategy4 - list of the [standard cells](https://www.zerotoasiccourse.com/terminology/standardcell/) used by your design
* runs/wokwi/results/final/gds/user_module.gds - the final [GDS](https://www.zerotoasiccourse.com/terminology/gds2/) file needed to make your design

# What next?

* Share your GDS on twitter, tag it #tinytapeout and [link me](https://twitter.com/matthewvenn)!
* [Submit it to be made](https://docs.google.com/forms/d/e/1FAIpQLSc3ZF0AHKD3LoZRSmKX5byl-0AzrSK8ADeh0DtkZQX0bbr16w/viewform?usp=sf_link)
* [Join the community](https://discord.gg/rPK2nSjxy8)
