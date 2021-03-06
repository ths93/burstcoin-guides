!!! danger
    Before you start, we strongly advise you to read the according [Burstwiki page on plotting](https://burstwiki.org/wiki/Technical_information_to_create_plot_files) and the [Burstwiki page on mining](https://burstwiki.org/wiki/Technical_information_about_mining_and_block_forging). 

In order to mine Burst, you first have to plot the disk space you want to use. Plotting may be a time and energy-consuming task, however it only has to be done once.

The disk space you dedicate to Burst can't be used otherwise once plotted (unless you delete the plot files) so make sure you can truly afford the space dedicated to mining Burst.

HDD disk space will be occupied by **plot files**. Plot files are like bingo cards that contain pre-solved responses to the cryptographic problem that the blockchain poses to miners each and every round.

!!! tip
    Find out how much you can make with the capacity at your disposal using a [mining calculator](https://explore.burst.cryptoguru.org/tool/calculate).

Plotting the disk space you wish to dedicate to mining Burst can be accomplished multiple ways, several plotters exist for different operating systems. CPU based plotters (in contrast to GPU based plotting software) generally create optimized plot files. This means your plot files will be of the highest possible quality and efficiency. So be aware, how you are generating your plot files.

!!! info "Plot files"
    There are a few things you have to understand to get a general overview of the nature of plot files.

    Plot files consist of **nonces** which contain the cryptographic solutions you will be mining with.

    * **1 nonce = 262144 bytes**

    Plot file size is measured in nonces so you will have to convert the size of your dedicated disk space to nonces. Nonce calculators exist to make this process easier.

    Nonces are ordered **linearly** in **sequential order**. the number they're assigned to is arbitrary but they should **never overlap** (overlapping reduces plot efficiency and triggers an error in most mining software).
