
## 3 Now, from the command line!

Download the file seq-align.zip from Blackboard, noting where exactly in your filesystem you are placing it. Now, open the Terminal.

```bash
# First, move into the MBLS207 folder (if you are working
# with Windows, this should ideally be in your Linux
# home folder)
cd <path-to-MBLS207>

# Look at your location.
pwd
ls

# Copy the file you downloaded here, and look again
cp <path-to-downloaded-file>/seq-align.zip .
ls

# Look at this in different ways as well
ls -l
ls -lh

# Let's now prepare the stage by making this a bit tidier
mkdir software
cd software
pwd # Make sure you changed folder
mv ../seq-align.zip .
ls -l

# OK now we are finally going to deal with this file. Go
# ahead and unzip it!
unzip seq-align.zip
```

&lt;page_number&gt;2&lt;/page_number&gt;

---


## Page 3

html
<table>
  <tr>
    <td>26</td>
    <td># The file should be uncompressed! Check it out</td>
  </tr>
  <tr>
    <td>27</td>
    <td>ls -l</td>
  </tr>
  <tr>
    <td>28</td>
    <td>cd seq-align/</td>
  </tr>
  <tr>
    <td>29</td>
    <td>ls -l</td>
  </tr>
  <tr>
    <td>30</td>
    <td></td>
  </tr>
  <tr>
    <td>31</td>
    <td># Now, we need to install it. To do that, first you move into the unzipped folder, and then you use the common install command, 'make':</td>
  </tr>
  <tr>
    <td>32</td>
    <td>make</td>
  </tr>
  <tr>
    <td>33</td>
    <td></td>
  </tr>
  <tr>
    <td>34</td>
    <td># If you have problems with 'make': check the notes at the end of the tutorial</td>
  </tr>
  <tr>
    <td>35</td>
    <td></td>
  </tr>
  <tr>
    <td>36</td>
    <td># After a bunch of ugly lines in your terminal, which represent information about file compilation, the tool should be installed. Take a look and find the difference with what you saw above</td>
  </tr>
  <tr>
    <td>37</td>
    <td>ls -l</td>
  </tr>
  <tr>
    <td>38</td>
    <td></td>
  </tr>
  <tr>
    <td>39</td>
    <td># That bin folder appeared out of nowhere, right? Go within it and take a look</td>
  </tr>
  <tr>
    <td>40</td>
    <td>cd bin</td>
  </tr>
  <tr>
    <td>41</td>
    <td>ls -l</td>
  </tr>
  <tr>
    <td>42</td>
    <td></td>
  </tr>
  <tr>
    <td>43</td>
    <td># needleman-wunsch and smith-waterman are the two software you will use here. In order to see if they work, you can run them without arguments</td>
  </tr>
  <tr>
    <td>44</td>
    <td>./needleman_wunsch</td>
  </tr>
  <tr>
    <td>45</td>
    <td>./smith_waterman</td>
  </tr>
  <tr>
    <td>46</td>
    <td></td>
  </tr>
  <tr>
    <td>47</td>
    <td># The information printed to screen should be all you need to know to run the software. Congrats, now let's go back to your MBLS207 folder, create a folder for the next exercises, and you are ready to move ahead!</td>
  </tr>
  <tr>
    <td>48</td>
    <td>cd <path-to-MBLS207></path-to-MBLS207></td>
  </tr>
  <tr>
    <td>49</td>
    <td>mkdir tutorial3</td>
  </tr>
  <tr>
    <td>50</td>
    <td>cd tutorial3</td>
  </tr>
  <tr>
    <td>51</td>
    <td>pwd</td>
  </tr>
</table>
Well done. Let's now move ahead and perform your own alignments.

## Exercise 4

Create a FASTA file called 'two_mock_sequences.fasta' (using 'nano' in the command line, or using a plain text editor such as notepad or TextEdit (note: if you do this and save it elsewhere in your system, make sure to copy it to the tutorial3 folder using the terminal). Include in the file the following sequences in FASTA format:

```fasta
>Sequence1
GACGTAGCATCGACTGGCTAGC
```

&lt;page_number&gt;3&lt;/page_number&gt;

---


## Page 4

3 >Sequence2
4 GGCGCCGCTTCTGGGTAGC

Now align them using the Needleman-Wunsch algorithm. Note that in order to access the software, you need to provide your computer the path to the tool:

```bash
# Make sure of where the needleman-wunsch program is by
# completing the correct path here. Run the software
# without arguments or options, and it will show you
# information about its usage:
<path-to-MBLS207>/software/seq-align/bin/needleman-wunsch

# OK, now run it on your sequences:
<path-to-MBLS207>/software/seq-align/bin/needleman-wunsch
--file two_mock_sequences.fasta

# Yay! Now play around with the software and check what
# kind of output it can provide you
<path-to-MBLS207>/software/seq-align/bin/needleman-wunsch
--file two_mock_sequences.fasta --colour
<path-to-MBLS207>/software/seq-align/bin/needleman-wunsch
--file two_mock_sequences.fasta --pretty
<path-to-MBLS207>/software/seq-align/bin/needleman-wunsch
--file two_mock_sequences.fasta --colour --pretty
```

How many bases were found to match? How many mismatches? How many gaps?

**Exercise 5**

Run the same command but changing the gap extension penalty to -4 (hint: check out all possible software options by running it without any arguments or options). Does the result change? Which result do you trust more?

**Exercise 6**

Now run a local alignment of the same sequences by running the program smith-waterman. The software produces two different alignments. What regions of the two sequences do they concern?

**Exercise 7**

If your goal is to detect homologous sequences as a result of these alignments, what result do you trust more, and why?
