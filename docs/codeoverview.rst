
Code Overview
==============


"I have made this longer than usual because I have not had time to make it shorter."
-- Blaise Pascal

Mimpy is designed to be a very simple library, the core code is 
less than 10K lines. While it uses an Object Oriented structure, the functionality 
and data remains transparent to the user. 

   

There are two main classes, **Mesh** and **MFD**: 

.. image:: mesh_mfd.svg
   :align: center


As the name suggests, **Mesh** represents the geometry of the mesh that will be used for computation. 
In addition, a **Mesh** instance maintains information about boundary faces and some physical properties of the problem.  
Typically, the user will not interact with the **Mesh** class directly, but rather use subclasses and helper tools 
that make the task much easier. The user can also use files generated using standard mesh generation programs:

.. image:: mesh_sources.svg
   :align: center



The second class is called **MFD**, and stands for Mimetic Finite Difference. **MFD** takes a **Mesh** instance 
and constructs the appropriate linear system of equations that approximate diffusion problem. This is part is what
is called the "discretization" method, or in the parlance petroleum engineering, the "transmissiblity" calculation. 
The **MFD** class can set Dirichlet (pressure), Neumann (flux) boundary conditions, and forcing terms. 

The **Mesh** and **MFD** are sufficient for solving the diffusion equation. However, once you can solve that, you can 
also solve more complex physical problems. For this, we have a module of **models**. The **models** take an instance of 
**MFD** and **Mesh** and use them to solve physical phenomena like single-phase and two-phase flow.














