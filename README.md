# project1-sequence-analysis
Finding mutations within different samples
This project compares a 200-nt fission yeast sequencing reads against a reference sequence. It tests if samples that are treated with a genotoxic agent have more or different mutations, compared to untreated controls. 

### <ins> How do you run the program? </ins>
Open Google Colab. Click on 'File and then 'Open notebook' and then 'GitHub'. Paste the URL and open the notebook. 

### <ins> Inputs and Outputs </ins>
The inputs include 200-nt reference sequence, reference.txt and reads.csv. There are 6000 reads that each have read_id, sample, group and sequence. 

### <ins> Code design </ins>
#Counting separate from printing 
My first summarise_samples was one long function but found it too difficult to keep track of my code. Instead, splitting it into sections like count_read, finalise_record and two printing function kept my work more organised and easier to track.

#Reusing functions for Steps 4 and 5
calculate_percentage returned 'None' when there are no valid reads in a sample and allows the function to run without crashing or giving 0%. It is also used in Step 5 so invalid reads are excluded. 

### <ins> Testing </ins>
validate_read("ATN", "ATGA") returns ["wrong_length", "invalid_characters"]
Read with three mismatches- one at the final position (at 200) counts as one mismatch read but three mismatch events. 
If a sample has reads that are all invalid, then it returns as mismatch_percentage= None and not used in n in compare_positions. 
