# Collections of Cells, Binomial Ideals, and Gorenstein Property

This project is devoted to testing the following conjecture:

> If $P$ is a domino-stable collection of cells and $K[P]$ is not a domain, then $K[P]$ is Gorenstein.

---

## Directories

We provide two main directories:

1. **SageMath/**  
   - Contains the code to compute the set `L` of all collections of cells of a fixed rank `n`.  
   - The scripts generate the collections up to symmetries.  
   - Relevant code can be found in this directory.

2. **Macaulay2/**  
   - Contains the script `GorensteinTest.m2`.  
   - For each collection `Q` in `L`, the program:  
     * Computes the $h$-polynomial of the coordinate ring of `Q`.  
     * Tests if the inner 2-minor ideal $I_P$ is non-prime and the $h$-polynomial is palindromic.  
     * If both conditions hold, it tests whether $K[P]$ is Gorenstein.

Additionally, two `.zip` archives are provided:  
- One contains lists of collections of cells up to rank 8.  
- The other contains lists of polyominoes up to rank 11.  
These lists are in `.txt` format, ready to use with the Macaulay2 code.  

A collection is represented as a list `Q`, whose elements are the cells, each specified by its diagonal corners. For example:

```
      __
   __|__|
  |__|__|

 ``` 
is encoded as:  Q={{{1,1},{2,2}},{{2,1},{3,2}},{{2,2},{3,3}}} 

3. **Output_Pictures/**  
- Contains the Python script `From_List_To_Picture.py`.  
- This script takes as input the file `input_collections.txt` and generates a folder containing the corresponding visualizations of the collections.  
- The directory also includes all precomputed lists and images of collections of cells (up to rank 8) and polyominoes (up to rank 11) that are domino-stable, non-domain, and Gorenstein.


---------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------
 HOW TO USE
---------------------------------------------------------------------------------------------------

1. **Download the repository**  
   - From GitHub, click on *Code* → *Download ZIP*.  
   - Extract the `.zip` archive on your computer.  
   - You will now have a local folder containing the subdirectories `macaulay2/` and `sage/`.

2. **Prepare the data files**  
   - Inside the main repository, you will also find two archives:  
       * `Collections_of_cells_up_rank_8.zip`  
       * `Polyominoes_up_rank_11.zip`  
   - Extract these archives **into the `macaulay2/` directory**.  
   - After extraction, the `.txt` files with the collections will be available in the same folder where `RookPol.m2` is located.

3. **Run the code in Macaulay2**  
   - Open a terminal and navigate to the `macaulay2/` directory;
   - Start Macaulay2 and load the required package and script:  
     ```
     loadPackage "Binomials";
     loadPackage "TorAlgebra";
     load "TestGorenstein.m2";
     ```

4. **Test the conjectures**  
   - Load a file containing a list of collections of cells, e.g.:
     ```
     L = value get("weak_polyplets_n4.txt");
     TestGor(L);
     ```
   - This will test the conjectures for all collections in `L`.

5. **Additional functionality**  
   - The file `TestGorenstein.m2` also contains several auxiliary functions that can be used independently

---

