## Reduced model for the n-heptane kinetic model (LLNL, 2011) 

Date: Mar 07, 2023; Maintainer: Zhiwei Wang.

### Detailed kinetic model 

- Mechanism: LLNL_n-heptane_648sp_detailed.yaml
- See [Mehl M, Pitz W J, Westbrook C K, et al. Kinetic modeling of gasoline surrogate components and mixtures under engine conditions[J]. Proceedings of the Combustion Institute, 2011, 33(1): 193-200.](https://www.sciencedirect.com/science/article/pii/S1540748910000787?casa_token=OIW80_QsZB0AAAAA:I0alvoVky-3dZOqIFU-JCajEKagglHgnYbzjuKiXiD3ixFN7VeriIBfb_scKyTQzN2N_26UyQIk)
- Species num: *<font color=red>648</font>*
- Reactions num: *<font color=red>4846</font>*

### Model reduced by DeePMR

- Mechanism: LLNL_n-heptane_41sp_skeletal.yaml
- Species num: *<font color=red>41</font>*
- Reactions num: *<font color=red>292</font>*
- Overall average relative error: *<font color=red>19.1%</font>*

### Working condition

**Zero-dimensional homogeneous ignition under constant pressure**

- initial condition
    - Temperature: *<font color=red>600 ~ 1700 K</font>*
    - Pressure: *<font color=red>1 ~ 50 atm</font>*
    - Equivalence ratio: *<font color=red>0.5 ~ 2</font>*
- notice
    - The accuracy is slightly lower in the low temperature area.
- validation
    
    ![IDT](validation/IDT.png)


**perfectly stirred reactors**
- initial condition
    - Temperature: *<font color=red>298 ~ 500 K</font>*
    - Pressure: *<font color=red>1 ~ 50 atm</font>*
    - Equivalence ratio: *<font color=red>0.5 ~ 2</font>*
- validation
    ![PSR](validation/PSR_T=298K.png)
    ![PSR](validation/PSR_T=500K.png)


**One-dimensional premixed laminar flame** 
- initial condition
    - Temperature: *<font color=red>around 298 K</font>*
    - Pressure: *<font color=red>1 ~ 50 atm</font>*
    - Equivalence ratio: *<font color=red>0.5 ~ 2</font>*
- validation
    ![Flame speed](validation/Flame_phi_298K_log.png)
    ![Flame speed](validation/Flame_phi_298K_log_with_other_paper.png)

### DNN loss
This picture shows the DNN loss history during iterative sampling. The SGD optimizer and mean square loss function are used for training such DNN model.
![DNN loss](validation/loss_his.png)