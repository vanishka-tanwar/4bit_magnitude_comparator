# 4bit_magnitude_comparator





# Openlane Workflow

## Step 1: setting OpenLane and SKY130 PDK 

```sh
git clone https://github.com/efabless/openlane.git openlane
cd openlane 
make openlane 
make pdk

> add this configuration variable
export PDK_ROOT=<absolute path to where skywater-pdk and open_pdks will reside>

> add library 
export STD_CELL_LIBRARY=<Library name>
make full-pdk

```

        - sky130_fd_sc_hd
        - sky130_fd_sc_hs
        - sky130_fd_sc_ms
        - sky130_fd_sc_ls
        - sky130_fd_sc_hdll
 

## Step 2: Test

On successful completion of previous step, lets test it by

```sh

make test
```

which shall display the "successful" message. 

> **Note:** Go to next steps only after having the **successful test**.

**Next steps**

## Step 3: Opening OpenLane in Docker

If docker is installed, if you can see the docker version 19.* and above then docker is present and go to next step else install docker manually

```sh
docker --version


```

you can install docker file following this link 

https://docs.docker.com/engine/install/


## Step 4: Running openlane

Once you are sure the docker is present, you have to make mount of the current files in **openlane**

```sh
make mount

```
Now lets test a design which is already present in `openlane/designs` type 

```sh
bash-4:$ ./flow.tcl -design dvsd_cmp -interactive 
```

```sh
bash-4:$

./flow.tcl -design dvsd_cmp -tag <wher you tag this file name>

> which shall display the "successful" message. 

```

## Step 5: magic layout generate 


```sh
bash-4:$

magic <file name>

```
