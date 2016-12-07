##DNA Sequence De Novo Assembly

This repo contains an implementation of a solution to DNA sequence assembly problem. The is based on Euler Walk on De Bruijn Graph constructed using kmer representation. 

(For further details, please read docs/Description.md)


###Prerequisites
The following only represents one set of configurations of the libraries used in development.
```
python >= 2.7.11
nose
numpy >= 1.7.1
biopython >= 1.65
networkx == 1.11
matplotlib == 1.5.3
```

###How to run the code
To run the dummy_data.fasta:  
```$ python ./de_novo_assembly/run.py -i ./data/dummy_data.fasta -k 6 --print_to_console```

To include a graph, simply add the option as '--graph':  
```$ python ./de_novo_assembly/run.py -i ./data/dummy_data.fasta -k 6 --print_to_console --graph```

To run the 50 fasta record set:  
```$ python ./de_novo_assembly/run.py -i ./data/coding_challenge_data_set.fasta -k 20 --print_to_console```

The k is set to 20 for the 50 fasta record dataset for stable result. The graph plotting feature is very primitive and may not work well for large De Bruijn Graph visualization. A sample plot for the dummy data of 4 fasta records can be found here for a 17 node 5mer De Bruijn Graph for a total 19 bp assembly.

![Image of dummy dataset DBG](https://github.com/guojingyu/DeNovoAssembly/blob/master/dummy_data_de_bruijn.png)

For all running options:  
```
$ python ./de_novo_assembly/run.py -h
usage: run.py [-h] [-i INPUTFASTAFILE] [--reverse_complement] [-k KMERLENGTH]
              [--graph] [-o OUTPUTFILE] [--output_longest_assembly]
              [--print_to_console]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUTFASTAFILE, --inputfastafile INPUTFASTAFILE
                        fasta formatted text file containing the sequences for
                        assembly
  --reverse_complement  include to the reverse complement sequences of the
                        fasta file sequence
  -k KMERLENGTH, --kmerlength KMERLENGTH
                        parameter k to control the length of kmer as the edge
                        of De Bruijn Graph
  --graph               plot the De Bruijn Graph constructed from kmer of the
                        input sequence
  -o OUTPUTFILE, --outputfile OUTPUTFILE
                        output assembled DNA sequences into file with input
                        name and time stamp appended
  --output_longest_assembly
                        output the longest assembled DNA sequence. If more
                        than one same longest DNA sequence found, return the
                        first one in rank
  --print_to_console    true or false to print assembled DNA sequence to
                        console
```



