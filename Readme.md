# Readme: Get started.

## This archive contains the following:
   - A Jupyter notebook which contains the pipeline in an intuitive way and the results of the the said experiment.
   - A python code file which contains the code required to conduct the Sequence extraction
   - An simple text-based readme file which provides the user with the instructions on how to start.

### The source file is in an .faa format which can be downloaded from [here](https://www.ole.bris.ac.uk/bbcswebdav/pid-6233191-dt-content-rid-23562934_2/xid-23562934_2) or [here](https://github.com/KevinDayve/Group-project/blob/main/NewYersinia.faa)

To run blast on your local computer, you need to install a standalone blast software on your local computer. To download the latest blast software, go to this [website](https://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/) and download a software which best suits your PC type (whether your PC is a 32 bit or a 64 bit. **It is very important that you download the correct software**.
* Now go to the folder/drive containing the downloaded blast executable, run the installation and save the BLAST+ in your desired directory (Left to it's   default it will download itself in your C:// Drive).
* Once you have installed, to check whether the installation has run smoothly, go to the folder or path containing your BLAST software and in the address     bar type 'CMD' or open command prompt and change the directory to the one which contains your BLAST software using the CD function. More on how to use the cd command can be found [here](https://www.howtogeek.com/659411/how-to-change-directories-in-command-prompt-on-windows-10/) or in case you are a Mac user,   check [here](https://www.howtogeek.com/659411/how-to-change-directories-in-command-prompt-on-windows-10/).
* After you have done that, type the keyword 'blastx -h' just to make sure that the command is recognised by the terminal which means that the installation   was done correctly.

### Make a local database.
Now you would want to run your sequences of interest against a database. To create a database is rather in simple in blast. You will need the following:
	- a .faa or .fa file containing all the sequences.
	- a .txt file of the sequences you want to conduct the blast against.
In this case, our sequences of interest were the four genes comprising of the lysis casette TC-PAIY of the enterocolata strain. You want to copy them and store them in a single .txt file.
Now move both of them (the .faa/.fa file and the .txt file) to the folder which contains the Blast software. To make a local blast database, you need to:
* Open the command prompt (Make **sure** that both the files in the same folder as your blast software).
* Use the **makeblastdb** command to create a new database, So the command in this instance would look like this: makeblastdb -in name.faa -dbtype prot -  out NewYersinia
     - Here **db** stands for database,
     - the **-in** command asks you for the name of your .faa or .fa file which contains the series of sequences.
     - **-dbtype** is the type of database you want to create, in our case, we need a protein database so we type 'prot'.
     - and the **-out** is the name that you want for your database, here we were dealing with a yersinia strain so we named it 'NewYersinia'.

### Run a local blast.
You can run a blast search in the command prompt by using the blastp query method. Blastp is used for protein-protein blasts. To run a blast search of your targeted sequences against the now newly created database. You have to:
* Open the command prompt and type: blastp query Sequence.txt db NewYersinia -out results.txt -outfmt 6
* Let's break down the above command:
  - **blastp** is a keyword you want for a protein-protein blast.
  - **query** is again a keyword wherein you have to enter the name of the file on which you want to run the blast, in this case, it was a file called     Sequence.txt
  - **db** is where you have to enter the name of the database you want to run the sequence against, here it was NewYersinia.
  - **out** is the name of the file you want to contain all your blast results.
  - **outfmt 6** will store the results in a tabular format.

### Extract Sequence based on IDs.
Upon interpretation of the BLAST results one may want to peruse more closely into the database and extract it's sequnces based on their accession IDs. 
But before we do anything, we would first want to install python, which you can install from their [website](https://www.python.org/downloads/).
* Then, copy the .py file containing the code to run multiple sequence extraction and paste it in the **same** folder containing your database file and your query   sequences.
* Open your command prompt from the folder containing all your files.
* Type Python seqextraction.py (It could be any name but make sure you add the .py extension) and the prompt would ask you to enter the name of the file.
* Enter the name of the file **including** the extension. (If you don't, the prompt would return an error and we do not want that.)

So, that should do it. Remember, any time you want to perform a sequence extraction make sure all the file are in the same folder.

## Acknowledgements:
While everyone contributed in some way to the project, but ultimately it was categorised as:

|**Name**     |**Role**   |
|---------|-------|
|**Yeuchen** | Identification & extraction of the gene in the lysis casette |
|**Kajal** | Interpretation and analysis of the BLAST results |
|**Grace** | Preparation of the pipeline and the concomitant jupyter notebook eliciting the same. |
|**Kevin** | Producing the code, and the Get started text based markdown file | 










 
