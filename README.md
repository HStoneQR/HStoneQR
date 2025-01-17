- 👋 Hi, I’m @HStoneQR
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
HStoneQR/HStoneQR is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
I developped a sparse QR solver for large scale linear system in Python. If you have some hard problems 
(sparse matrix, each node has just a few neighbors, like in finite difference/ finite element analysis) 
to solve, and your iterative solver could not converge, then you can try with me for free at first. 

Feel free to drop me an email at HStoneQR@gmail.com to share your matrix download link (<1G for bandwidth consideration) 
or python script to generate your matrix and your proposed bid price if a solution is found for a nonsingular matrix. 

UPDATE 1/16/2025:
add option to use hdf5 (h5py package) as cache if the matrix R is too large to fit in memory. 
call blas level 3 to speed up the matrix multiplication in compact WY compact wy representation


Some references:

https://ecommons.cornell.edu/bitstreams/7ee58710-219e-435b-8465-2093e431c2a7/download

https://icl.utk.edu/~mgates3/docs/lapack.html

https://docs.scipy.org/doc/scipy/reference/linalg.blas.html


--Matrix reordering:

matrix reordering is very important in solving linear systems, it can dramatically speed up the iterative method like gmres/cg.
Also it will dramatically reduce the memory usage in Direct solver like QR for general linear system or cholesky decomposition for 
symmetric linear system.

https://github.com/inducer/pymetis

https://docs.scipy.org/doc/scipy/reference/generated/scipy.sparse.csgraph.reverse_cuthill_mckee.html

https://people.engr.tamu.edu/davis/publications_files/An_Approximate_Minimum_Degree_Ordering_Algorithm.pdf

--Out of core computing

There are several tools in python to do it

https://numpy.org/doc/stable/reference/generated/numpy.memmap.html

https://docs.h5py.org/en/stable/quick.html#quick

https://www.pytables.org/usersguide/tutorials.html

memmap needs to declare the shape at creation and we can only get an estimated upper bounds for memory usage for R the upper triangular matrix 
and it will waste many storages and seems having no compression option. So I turned to use h5py to write the R in chunks.

to be continued...






