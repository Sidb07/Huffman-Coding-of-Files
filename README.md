## Huffman Coding for text files
 This project is based on Huffman Coding, a lossless, bottom-up compression algorithm. It can compress and decompress any text files.

 To learn more about Huffman Coding and its applications in Information Theory read [this](https://en.wikipedia.org/wiki/Huffman_coding) article.

### Implementation in Project
 This project supports two functions:
 1) Encode: Compresses input file passed.
 2) Decode: Decompresses Huffman coded file passed back to its original file.

 `struct Node` represents a node of Huffman Tree which is generated during compression or decompression of files. It stores character data, its frequency, Huffman code, and two pointers that point towards the left or right node if they exist.

 Huffman class contains only two public functions
 1) compress()
 2) decompress()
 And a constructor which accepts input file and output file. The object of this class can be initiated as follows: `huffman h(inputFileName, outputFileName);`

 **Compressing file** `compress()`: Following are the steps followed to compress the input file.

 1)`createMinHeap()`: This function reads the input file and stores the frequency of all the characters appearing in the file. It further creates a Min Heap structure based on the frequency of each character using priority queue as a data structure that stores Nodes and uses its frequency as a comparing parameter.

 2)`createTree()`: This function generates the Huffman tree by duplicating the Min Heap created earlier keeping the original Min Heap. It pops the two Nodes with the lowest frequency. Further, it assigns these two as left and right nodes to a new Node with a frequency which is the sum of the two popped nodes and pushes this Node back to the Min Heap. This process is continued until Min Heap has a size equal to 1.

 3)`createCodes()`: This function traverses the entire Huffman tree and assigns codes in binary format to every Node.

 4)`saveEncodedFile()`: This function saves the Huffman encoded input file to the output file. The image below illustrates how the output file is written.