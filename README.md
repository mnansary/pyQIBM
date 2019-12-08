# Repo For IBM Q with Qiskit


        Author:MD Nazmuddoha Ansary  
        Version:0.0.1  

![](/src_img/python.ico?raw=true )
![](/src_img/qiskit.ico?raw=true)


# Requirements
* qiskit==0.13.0
> create virtualenv
> pip3 install -r requirements.txt

**Note:** for manuall installation of **QISKIT** please keep in mind that some circuit drawing may not be plotted in line without **ipywidgets**

## Getting Started:
* install the requirements
* Create An Account on [IBM Q Experience](https://www.ibm.com/quantum-computing/technology/experience/)
* Collect token

![](/src_img/token.png?raw=true )

* Save token in **token.txt**
* Open **SaveAccount.ipynb** and check if the account was successfully saved.

# NoteBooks:

## QunatumTeleportation.ipynb

**Quantum teleportation** is a process in which quantum information *(e.g. the exact state of an atom or photon)* can be transmitted (exactly, in principle) from one location to another, with the help of classical communication and previously shared quantum entanglement between the sending and receiving location. Because it depends on classical communication, which can proceed no faster than the speed of light, it cannot be used for faster-than-light transport or communication of classical bits. [source](https://en.wikipedia.org/wiki/Quantum_teleportation)

**PLEASE NOTE THAT:**
* This **Does NOT** mean we can trasnport a **qbit physically from one place to another**
* This is a tranformation of **quantum information** from one place to another

### BUT WHATS SO IMPORTATNT ABOUT THIS?
Well, in a classical computer we copy stuff from one place to another with absolutely no issue. But in a **Quantum Computer** you are actually not allowed to copy because the moment you try to copy you perfom an actual **measurement** which destroys the original states.So to copy the states we need to take advantage of **entanglement**. [Quantum Entanglement](https://en.wikipedia.org/wiki/Quantum_entanglement) 

**THE CODE IS STRICTLY BASED ON OFFICIAL QISKIT TUTORIALS.**
[QISKIT-COMMUNITY-TUTORIALS](https://github.com/Qiskit/qiskit-community-tutorials)



## BernsteinVazirani.ipynb
Based On: [Official QISKIT Community Tutorial](https://github.com/Qiskit/qiskit-community-tutorials) 

The **Bernstein–Vazirani algorithm**, which solves the Bernstein–Vazirani problem is a quantum algorithm invented by Ethan Bernstein and Umesh Vazirani in 1992. It's a restricted version of the **Deutsch–Jozsa algorithm** where instead of distinguishing between two different classes of functions, it tries to learn a string encoded in a function. 
The Bernstein–Vazirani algorithm was designed to prove an oracle separation between complexity classes **BQP and BPP**.[SOURCE](https://en.wikipedia.org/wiki/Bernstein%E2%80%93Vazirani_algorithm)

Problem Statement:
say you have a **n** digit number *(we will handle binary)*: (1010010101001........)  . 
How can a classical computer find this number??
To give an example: say the number is 111000
We can:
* start from 000000
* increse by 1 
* get the difference
* when diff==0 found number.
But that would take **2^6=64** tries (worst case).
**COMPUTERS ARE SMART**(Even classical ones)
It would actually find the number in **6** steps.
What it would do is :
* take the number of bits in the number and do **AND operation** with the secret number:
    
        111000  
        000001  
        ------  
        000000  <-- Bit Wise And Operation  
        
* now just from the result it can say that the last digit is **0** because if it was **1** the last digit of the and would be **1**
* then for the second digit:
        
        111000  
        000010  
        ------  
        000000  
        
* and till the last digit:
        
        111000
        100000
        ------
        100000

Ok that was good. So a digit of length **n can be found in n** shots.

**NOW IS THE COOL PART**.A quantum computer can find this number of any length with *(yes you guessed that right)* **1** shot. 

This algorithm is a good demonstration of how a quantum computer outperforms a classical computer.


## BitStringQIR.ipynb

Quantum Image Representation of a binary Image with **bitstring compression**.

### BitString Compression
To store a bit string of length **n** in a classical computer we will need to use **n** bits. 
For the same purpose, in a quantum computer it is enough to use only **log2(n)+1** qubits.The way for that is to write down the bit string in the notation where firsts qubits describe the position (address) in a bit string, and the last one, the value on this position



# QUICK INFO 

### Qiskit Setup (For Ubuntu with Jupyter-notebook)
The [official way](https://qiskit.org/documentation/install.html) with conda **conda**.For installing without conda:  
* install virtualenv: ```pip3 install virtualenv```
* create a virtualenv: ```virtualenv venv``` 
* activate: ```source venv/bin/activate```
* install **ipykernel**: ```pip3 install ipykernel```
* add your venv to jupyter:  ```python3 -m ipykernel install --user --name=venv```
* list kernels to confirm: ```jupyter kernelspec list```
* create notebooks using the **venv** created. **NOT WITH PYTHON3**

### Environment 

    OS          : Ubuntu 18.04.3 LTS (64-bit) Bionic Beaver        
    Memory      : 7.7 GiB  
    Processor   : Intel® Core™ i5-8250U CPU @ 1.60GHz × 8    
    Graphics    : Intel® UHD Graphics 620 (Kabylake GT2)  
    Gnome       : 3.28.2  



### Sources (basics of QM ,Quantum Computation,Linear Algebra,Qiskit):
* [MIT open courseware: 8.04 By Prof.Allan adams](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) **QM**
* [Mathemetical Physics Lectures By Prof.Carl Bender](https://www.youtube.com/watch?v=LYNOGk3ZjFM&list=PLOFVFbzrQ49TNlDOxxCAjC7kbnorAR1MU) **Perturbation|Advanced**
* [Essence of Linear Algebra by 3Blue1Brown ](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)
> Quantum Computation is mostly linear algebra 
* [Qiskit Textbook](https://community.qiskit.org/education/)
