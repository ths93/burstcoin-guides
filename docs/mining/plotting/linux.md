## Plotting

Plotting on Linux is either done with the [cg_obup plotter](https://github.com/PoC-Consortium/cg_obup) or the [omdcct plotter](https://github.com/alter3d/omdcct).
Detailed setup instructions can be found on the respective github pages.

!!! hint
    When plotting your drive be careful to correctly use your numeric account id as KEY. In addition, pay attention to which nonces you are plotting (`startnonce` and `nonces` parameter). Every nonce should exist only once on your drives.

!!! warning
    All plot files are generated account-dependent, therefore changing accounts for mining, forces you to plot your files again.

!!! tip "Example"
    The following command starts the plotting process **as background process** for a `2T` plot file in `/sdd1/plots` on a machine with at least `32GB` on `4 cores` in `asynchronous` mode.
    The plot file will be associated with the account `11642189530862802431`.

    ```
    nohup ./plot64 -k 11642189530862802431 -x 1 -d /sdd1/plots -m 15G -s 0 -n 2T -t 4 -a > output.log 2>&1 &
    ```

    Each plot file has the following naming convention.
    ```
    <account_id>_<startnonce>_<nonces>_<nonces>
    ```
    e.g. our first command plots this file.
    ```    
    11642189530862802431_0_8388608_8388608
    ```

    This means for the next plotting process which plots the next file, we need to start at nonce:

     `previous startnonce` + `previous nonces plotted` + `1`

    --> `0` + `8388608` + `1` = `8388609`

    and we plot the next file.

    ```
    nohup ./plot64 -k 11642189530862802431 -x 1 -d /sdd1/plots -m 15G -s 8388609 -n 2T -t 4 -a > output.log 2>&1 &
    ```

    This process can be repeated till all your desired disk space is filled with subsequent plot files.
