# fastq-quality-nucleotide-sequence

Python project for 

* (i) [FASTq Quality Nucleotide Sequence](#fastq-qns) - implementation of the Phred Quality Score concept based on FASTq files (bioinformatics) ([usages](#all-usages))

> Text-based structure/format for storing both a biological sequence (e.g., usually nucleotide sequences) and their corresponding quality scores

## Dependencies

The dependencies `argparse` and `math` are native to Python platform.

## Contact / License

Feel free to contact me by mail: guilherme.farto@gmail.com

---

<a name="fastq-qns"></a>
## FASTq Quality Nucleotide Sequence (fastq-quality-nucleotide-sequence.py)
> Based on the implementation of the Phred Quality Score concept for FASTq files (bioinformatics)

Usage:
```python
python fastq-quality-nucleotide-sequence.py [-h] -ns NUCLEOTIDE_SEQUENCE [-ab ASCII_BASE]
```

The arguments are:

`-ns NUCLEOTIDE_SEQUENCE, --nucleotide_sequence NUCLEOTIDE_SEQUENCE` *(required)*
* nucleotide sequence to be checked based on average quality

`-ab ASCII_BASE, --ascii_base ASCII_BASE` *(optional but default value is "ASCII_33")*
* ascii base to be used to check the average quality of the nucleotide sequence

<a name="all-usages"></a>
## Usages

### Phred Quality Score calculation for the nucleotide sequence:
#### !02ABA85334519ABA0! (with ASCII Base 33 - Illumina):

```python
python fastq-quality-nucleotide-sequence.py -ns "!02ABA85334519ABA0!"
```

Output:

```
  Nucleotide Sequence..............: !02ABA85334519ABA0!
  ASCII Base.......................: ASCII_33
  Pre-Processed Sequence...........: 0 + 15 + 17 + 32 + 33 + 32 + 23 + 20 + 18 + 18 + 19 + 20 + 16 + 24 + 32 + 33 + 32 + 15 + 0
      Sum of Quality Values........: 399
      Number of Elements...........: 19
  Average Quality..................: 21
  Average Probability of Error P...: 0.001
```

### Phred Quality Score calculation for the nucleotide sequence:
#### !''\*((((\*\*\*+))%%%++)(%%%%).1\*\*\*-+\*''))\*\*55CCF>>>>>>CCCCCCC65 (with ASCII Base 33 - Illumina):

```python
python fastq-quality-nucleotide-sequence.py -ns "!''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65"
```

Output:

```
  Nucleotide Sequence..............: !''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65
  ASCII Base.......................: ASCII_33
  Pre-Processed Sequence...........: 0 + 6 + 6 + 9 + 7 + 7 + 7 + 7 + 9 + 9 + 9 + 10 + 8 + 8 + 4 + 4 + 4 + 10 + 10 + 8 + 7 + 4 + 
                                     4 + 4 + 4 + 8 + 13 + 16 + 9 + 9 + 9 + 12 + 10 + 9 + 6 + 6 + 8 + 8 + 9 + 9 + 20 + 20 + 34 + 
                                     34 + 37 + 29 + 29 + 29 + 29 + 29 + 29 + 34 + 34 + 34 + 34 + 34 + 34 + 34 + 21 + 20
      Sum of Quality Values........: 904
      Number of Elements...........: 60
  Average Quality..................: 15
  Average Probability of Error P...: 0.01
```

### Phred Quality Score calculation for the nucleotide sequence:
#### !02ABA85334519ABA0! (with ASCII Base 64 - Old Illumina):

> The values in this example do not reflect a real scenario - it only exemplifies the use of ASCII 64 instead of ASCII 33

```python
python fastq-quality-nucleotide-sequence.py -ns "!02ABA85334519ABA0!" -ab ASCII_64
```

Output:

```
  Nucleotide Sequence..............: !02ABA85334519ABA0!
  ASCII Base.......................: ASCII_64
  Pre-Processed Sequence...........: -31 + -16 + -14 + 1 + 2 + 1 + -8 + -11 + -13 + -13 + -12 + -11 + -15 + -7 + 1 + 2 + 1 + -16 + -31
      Sum of Quality Values........: -190
      Number of Elements...........: 19
  Average Quality..................: -10
  Average Probability of Error P...: 10
```
