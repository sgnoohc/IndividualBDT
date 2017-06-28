# Running MadGraph 5 example to generate 10k events for VBF/ttbar/WW+2j

First download a copy of madgraph 5.

    wget https://launchpad.net/mg5amcnlo/2.0/2.5.x/+download/MG5_aMC_v2.5.5.tar.gz

Untar the package.

    tar xvzf MG5_aMC_v2.5.5.tar.gz

Run to generate codes to generate events for the following processes.

    ./MG5_aMC_v2_5_5/bin/mg5_aMC mg5cards/proc_card_mg5__vbfhww.dat
    ./MG5_aMC_v2_5_5/bin/mg5_aMC mg5cards/proc_card_mg5__ttbar.dat
    ./MG5_aMC_v2_5_5/bin/mg5_aMC mg5cards/proc_card_mg5__ww2j.dat

Go to each code and generate 10000 events.
When prompted for options, press 0 enter, 0 enter.

    cd pp_hjj_jjlpvllmvlx
    ./bin/generate_events
    # 0 enter, 0 enter.
    cd ../ # go back to parent directory

    cd pp_ttx_blpvlbxlmvlx
    ./bin/generate_events
    # 0 enter, 0 enter.
    cd ../ # go back to parent directory

    cd pp_wpwmjj_jjlpvllmvlx
    ./bin/generate_events
    # 0 enter, 0 enter.
    cd ../ # go back to parent directory

Done!
