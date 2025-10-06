Student Info: Name: Anthony Villalobos Student ID: 008394627 Repo Link: https://github.com/villaloban/cs315Huffmanp1.git

Collaboration & Sources: The sources that I used in this project mainly involve resources for the readword function. Since we were working with instream I went on cplusplus.com to look at all the differen member functions that could be used with instream and found that get and peek were very useful when tokenizing our word. I also looked at the ascii value table to see which letters would be valid and which would be unvalid. During my testing I was having issues with some char being different even though they shouldn't have been and asked chat gpt what may be wrong with my code and it pointed out that I was using a regular char instead of an unsigned char making it so it would also include negative ascii numbers instead of just 0 - 255. I also collaberated with a classmate Gemma on our logic and thinking on how to solve the tokenization problems.

Implementation & Details: This project uses a scanner class to read from a file and tokenize the words making them form the basis of the frequency counting and Huffman coding. In order for it to be tokenized it must follow these exact rules Rules:

1. Lowercase the entire input (ASCII only).

2. A token is letters a–z with optional internal apostrophes.

3. Allowed patterns: [a–z]+ or [a–z]+’[a–z]+ (apostrophes only between letters).

4. Drop leading/trailing apostrophes.

5. Treat the following as separators (never part of tokens):
digits and numbers,
whitespace,
punctuation and symbols (including quotes and hyphens/dashes such as -, –, —),
any non-ASCII byte.

The Functions used in this implementation include:
Scanner(std::filesystem::path inputPath)
isLetter(char& c)  //lowers a char and checks if its a valid letter
string Scanner::readWord(std::istream &in)  //Reads a char from a stream and checks if it meets all the requirments for tokenization and if it does it returns the token
error_type Scanner::tokenize(std::vector<std::string>& words) //reads from an input file and stores the token in a vector
error_type Scanner::tokenize(std::vector<std::string> &words, const std::filesystem::path &outputFile) //writes the tokenized word into a .token output file

Testing & Status: Input;   bash compile_and_test.bash the_dominant_primordial_beast.txt
//this output means that there is no diff meaning its working as intended
Output: Compiling project...
Running program with input file 'input_output/the_dominant_primordial_beast.txt'...
diff input_output/the_dominant_primordial_beast.tokens /home/faculty/kooshesh/cs315_f2025_p3_part1/part1_tokens_files//the_dominant_primordial_beast.tokens

The .tokenized words end up looking like
chapter
iii
the
dominant
primordial
beast
the
dominant
primordial
beast
was
strong
in
buck

