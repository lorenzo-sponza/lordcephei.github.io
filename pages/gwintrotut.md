---
layout: page-fullwidth
title: "LM Tutorial"
subheadline: ""
show_meta: false
teaser: ""
permalink: "/lmtut/"
sidebar: "left"
header: no
---
<hr style="height:5pt; visibility:hidden;" />
# Introduction to GW calculations 

This tutorial carries out an LDA calculation for Si, starting from an init file. Following this are demonstrations of both QSGW and 1-shot GW calculations. The starting point is a self-consistent LDA calculation, which can be run with the following commands (click on the LDA self-consistency dropdown menu). More details on the set up and running of a self-consistent LDA calculation can be found on the fpintrotut page. 

<hr style="height:5pt; visibility:hidden;" />
### Command summary     
<div onclick="elm = document.getElementById('foobar'); if(elm.style.display == 'none') elm.style.display = 'block'; else elm.style.display = 'none';"><button type="button" class="button tiny radius">Click to show.</button></div>
{::nomarkdown}<div style="display:none;margin:0px 25px 0px 25px;"id="foobar">{:/}

    $ cp path/init.si .                                    #copy init file to working directory
    $ blm init.si --express --gmax=5 --nk=4 --nit=20 --gw  #use blm tool to create actrl and site files
    $ cp actrl.si ctrl.si                                  #copy actrl to recognised ctrl prefix
    $ lmfa ctrl.si; cp basp0.si basp.si                    #run lmfa and copy basp file
    $ lmf ctrl.si > out.lmfsc                              #make self-consistent

{::nomarkdown}</div>{:/}

Note that we have included an extra --gw switch. This switch tailors the ctrl file for a GW calculation. To see how it affects the ctrl file, try running blm without --gw. One consequence of --gw is that blm autogenerates a GW category. Its tokens mostly hold parameters that go into the GW input file (GWinput), which will be used in the QSGW step when it is generated later. 



