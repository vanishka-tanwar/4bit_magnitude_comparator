# 4bit_magnitude_comparator




# Openlane Workflow

## Step 1: Setting OpenLane

```sh
git clone https://github.com/efabless/openlane.git openlane
cd openlane 
make openlane 
make pdk

```
## step 2: Install SKY130 PDK 

```sh

export PDK_ROOT=<absolute path to where skywater-pdk and open_pdks will reside>
```       
Installed and add this configuration variable
```sh
export STD_CELL_LIBRARY=<Library name>
```       
the library names is one of:

- sky130_fd_sc_hd
- sky130_fd_sc_hs
- sky130_fd_sc_ms
- sky130_fd_sc_ls
- sky130_fd_sc_hdll
       
       
you can install all SKY130  
```sh

make full-pdk
```       
 

## Step 3: Test

On successful completion of previous step, lets test it by

```sh

make test
```

which shall display the "successful" message. 

> **Note:** Go to next steps only after having the **successful test**.

**Next steps**

## Step 4: Opening OpenLane in Docker

If docker is installed, if you can see the docker version 19.* and above then docker is present and go to next step else install docker manually

```sh
docker --version


```

you can install docker file following this link 

https://docs.docker.com/engine/install/


## Step 5: Running openlane

Once you are sure the docker is present, you have to make mount of the current files in **openlane**

```sh
make mount

```
![T-1](https://user-images.githubusercontent.com/72103059/130253604-7a5e19f0-ce8b-4cce-a1a2-22f42684287b.png)

Now lets test a design which is already present in `openlane/designs` type 


```sh
bash-4:$

./flow.tcl -design dvsd_cmp -tag vanshika_4bit_magnitude_comparator

```
![Screenshot from 2021-08-20 20-35-29](https://user-images.githubusercontent.com/72103059/130254035-478f3f5b-6f26-461f-927a-5e2d54cdc5ce.png)


which shall display the "successful" message.
![T-20_successful](https://user-images.githubusercontent.com/72103059/130254369-d9112e33-d50c-4028-9c2a-1e8dba499c0d.png)


## Step 6: magic layout generate 


```sh
bash-4:$

magic dvsd_cmp.mag

```
![dvsd_cmp_magic_layout(1)](https://user-images.githubusercontent.com/72103059/130252784-d6a24a18-8b96-4bbc-874d-b9ff98215e30.png)
