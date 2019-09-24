# Bound Dark Energy #

This code presents the implementation in CAMB of the Bound Dark Energy model studied in:

1. A. de la Macorra and E. Almaraz, Physical Review Letters **121**, 161303 (2018); https://arxiv.org/abs/1805.01510
2. E. Almaraz and A. de la Macorra, Physical Review D **99**, 103504 (2019); https://arxiv.org/abs/1812.01133,

where Dark Energy is described by a dynamically-generated scalar field with an inverse power-law potential:
<img src="https://latex.codecogs.com/svg.latex?\Large&space;V(\phi)=c\frac{\Lambda_c^{4+\alpha}}{\phi^{\alpha}}" title="\Large V(\phi)=c\frac{\Lambda_c^{4+\alpha}}{\phi^{\alpha}}" />

Here <img src="https://latex.codecogs.com/svg.latex?\Large&space;c" title="\Large c" /> is a constant, <img src="https://latex.codecogs.com/svg.latex?\Large&space;\Lambda_c" title="\Large \Lambda_c" /> is the condensation scale of the scalar field and <img src="https://latex.codecogs.com/svg.latex?\Large&space;\alpha=2/3" title="\Large \alpha=2/3" />.

If you use this code, I would be very grateful if you cite these two papers. 

### Requisites ###
1. ifort (I use version 15.0.7 20160518)
2. odepack
3. openmp

### Installation ###
1. Go to `$CAMB`
2. Download `odepack.f`, `odepack_sub1.f` & `odepack_sub2.f` from https://people.sc.fsu.edu/~jburkardt/f77_src/odepack/odepack.html and place these files in `$CAMB/odepack`
3. Compile ODEPACK:
```
   cd $CAMB/odepack
   ifort -c odepack.f odepack_sub1.f odepack_sub2.f
   ar qc libodepack.a *.o
```                                
4. Link these libraries to CAMB (see Makefile)
5. Compile CAMB: 
```
make
```
6. Run the code:
```
./camb params.ini
```

### Change log ###
Modifications and comments are indicated by `erickdd.mm.yy`. See README_BDE.txt for more details

### Acknowledgments ###
This code is built upon the CAMB public code (November 16 release; https://camb.info/) and `equations_quint.f90` template for quintessence. 

### Contact ###
For comments, suggestions, etc, feel free to contact me: erickalmaraz@gmail.com
