# 4bit_magnitude_comparator




# Openlane Workflow

## Step 1: Setting OpenLane
![Screenshot from 2021-08-20 23-48-09](https://user-images.githubusercontent.com/72103059/130276762-69de11f4-4939-4e3c-ab17-bf02511f3042.png)


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

## Step 5: Pre-layout

Simulation

This is how you can simulate your design.
![pre_simulation_analysis](https://user-images.githubusercontent.com/72103059/130665947-3c5a53a2-b16a-4967-830f-0d05666ee605.png)

Pre-layout simulation waveform
![pre_gtkwave(3)](https://user-images.githubusercontent.com/72103059/130666317-a68d77f7-903c-40bf-a39d-03cc8cb1c178.png)



## Step 6: Running openlane

Once you are sure the docker is present, you have to make mount of the current files in **openlane**

```sh
make mount

```
![T-1](https://user-images.githubusercontent.com/72103059/130253604-7a5e19f0-ce8b-4cce-a1a2-22f42684287b.png)

Now lets test a design which is already present in `openlane/designs` type 
The following directory of design where the design is present is :
'vsdflow/work/tools/openlane_working_dir/openlane/designs/dvsd_cmp'


```sh
bash-4:$

./flow.tcl -design dvsd_cmp -tag vanshika_4bit_magnitude_comparator

```
![Screenshot from 2021-08-20 21-04-37](https://user-images.githubusercontent.com/72103059/130257853-c3fa439b-62a2-473c-bf85-9dc98b01542d.png)



which shall display the "successful" message after running all the respective tasks. 
![T-20_successful](https://user-images.githubusercontent.com/72103059/130254369-d9112e33-d50c-4028-9c2a-1e8dba499c0d.png)


## Step 7: Magic layout generate 
For magic layout generation in magic tool write this in terminal where you ran the above process

```sh
bash-4:$

magic dvsd_cmp.mag


```

Zoom-in view of IP Layout of dvsd_cmp design in Magic Tool.
![dvsd_cmp_magic_layout(1)](https://user-images.githubusercontent.com/72103059/130252784-d6a24a18-8b96-4bbc-874d-b9ff98215e30.png)

Zoom-out view of IP Layout of dvsd_cmp design in Magic Tool.
![dvsd_cmp_magic_layout](https://user-images.githubusercontent.com/72103059/130258107-6887d9b8-3f86-4420-b840-66234458f158.png)

## Step 8: Post layout simulation 
command for post layout simulation 
![post_simulation_analysis](https://user-images.githubusercontent.com/72103059/130666627-12de80a3-43c8-42b2-acaf-e94a7e83dc17.png)

Post layout simulation waveform
![Screenshot from 2021-08-22 00-39-47](https://user-images.githubusercontent.com/72103059/130666825-fbe27f9c-f186-4da5-9270-198c31676827.png)


