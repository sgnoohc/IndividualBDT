# Investigate whether individual BDT matters

## The idea

[6/28/17, 2:24:31 PM] Tae Min Hong Tae Min Hong: i wanna know in a real life scenario with some syst and mc stat, what to do  
[6/28/17, 2:24:35 PM] Tae Min Hong Tae Min Hong: and a table of what to do  
[6/28/17, 2:30:22 PM] Philip Chang: Hm idk where do we start?  
[6/28/17, 2:30:49 PM] Tae Min Hong Tae Min Hong: 2 bkg, 1 sig, a few variables, controlled stats  
[6/28/17, 2:31:15 PM] Tae Min Hong Tae Min Hong: we can control the modeling too at some point add syst  
[6/28/17, 2:31:21 PM] Tae Min Hong Tae Min Hong: do a toy analysis  
[6/28/17, 2:31:22 PM] Philip Chang: Yeah  
[6/28/17, 2:31:27 PM] Tae Min Hong Tae Min Hong: and a bunch of toy analyses  
[6/28/17, 2:31:31 PM] Philip Chang: And learn the rule of thumbs  
[6/28/17, 2:31:33 PM] Tae Min Hong Tae Min Hong: an analysis on analyses  
[6/28/17, 2:31:39 PM] Tae Min Hong Tae Min Hong: yeah  
[6/28/17, 2:31:46 PM] Philip Chang: I like  
[6/28/17, 2:31:52 PM] Tae Min Hong Tae Min Hong: could be in the methods and instrumentations journal  
[6/28/17, 2:32:07 PM] Tae Min Hong Tae Min Hong: cms is doing things like feed bdt into bdt etc  
[6/28/17, 2:32:13 PM] Tae Min Hong Tae Min Hong: i want to see what you gain etc  
[6/28/17, 2:32:18 PM] Tae Min Hong Tae Min Hong: btagging a mess like that too  
[6/28/17, 2:32:47 PM] Philip Chang: which toy example do we start  
[6/28/17, 2:32:59 PM] Tae Min Hong Tae Min Hong: VBF WW vs. ttbar, WW  

## Generating VBF/ttbar/WW+2j events

See the instruction readme [here](RunningMG5.md)

## Events

Output of 10k events each reside here:

    /afs/cern.ch/user/p/phchang/public/individual_bdt/lhes

The format follows the standardized ```lhe``` format. [1](https://en.wikipedia.org/wiki/Les_Houches_Accords), [2](https://arxiv.org/abs/hep-ph/0609017)

### Brief explanation of what they mean

For example, if one looks at the VBF H to WW event,

    vim /afs/cern.ch/user/p/phchang/public/individual_bdt/lhes/vbfhww_events.lhe

Line 489 - 499 has the following

        2 -1    0    0  501    0 +0.0000000000e+00 +0.0000000000e+00 +2.6164223290e+03 2.6164223290e+03 0.0000000000e+00 0.0000e+00 1.0000e+00    <-- incoming parton
        1 -1    0    0  502    0 -0.0000000000e+00 -0.0000000000e+00 -2.4676386977e+01 2.4676386977e+01 0.0000000000e+00 0.0000e+00 -1.0000e+00   <-- incoming parton
       25  2    1    2    0    0 -1.1410135246e+01 -4.8433363968e+01 +8.9822371116e+02 9.0824001529e+02 1.2497242957e+02 0.0000e+00 0.0000e+00    <-- Higgs
       24  2    3    3    0    0 +1.6774433195e+00 -1.7849822494e+01 +4.4237474850e+02 4.4612924997e+02 5.4904094389e+01 0.0000e+00 0.0000e+00    <-- W+
      -24  2    3    3    0    0 -1.3087578565e+01 -3.0583541474e+01 +4.5584896265e+02 4.6211076532e+02 6.8128150959e+01 0.0000e+00 0.0000e+00    <-- W-
        2  1    1    2  501    0 -3.9690153924e+01 +7.4644459156e+01 +1.6677825561e+03 1.6699238779e+03 0.0000000000e+00 0.0000e+00 1.0000e+00    <-- outgoing vbf jet
        1  1    1    2  502    0 +5.1100289170e+01 -2.6211095188e+01 +2.5739674813e+01 6.2934822822e+01 0.0000000000e+00 0.0000e+00 -1.0000e+00   <-- outgoing vbf jet
      -13  1    4    4    0    0 -2.4412130158e+01 -1.7198095015e+01 +2.9025550489e+02 2.9178756774e+02 0.0000000000e+00 0.0000e+00 1.0000e+00    <-- mu+
       14  1    4    4    0    0 +2.6089573477e+01 -6.5172747897e-01 +1.5211924362e+02 1.5434168222e+02 0.0000000000e+00 0.0000e+00 -1.0000e+00   <-- mu neutrino
       11  1    5    5    0    0 -1.6660090305e+01 -3.4925305860e+01 +4.5473556469e+02 4.5637897562e+02 0.0000000000e+00 0.0000e+00 -1.0000e+00   <-- e-
      -12  1    5    5    0    0 +3.5725117395e+00 +4.3417643853e+00 +1.1133979624e+00 5.7317896969e+00 0.0000000000e+00 0.0000e+00 1.0000e+00    <-- anti e neutrino
      ^^^                        ^^^^^^^^^^^^^^^^^ ^^^^^^^^^^^^^^^^^ ^^^^^^^^^^^^^^^^^ ^^^^^^^^^^^^^^^^ ^^^^^^^^^^^^^^^^
      pdgid                       X momentum        Y momentum        Z momentum        Energy            Mass

I think the comment I added above is enough to get started
