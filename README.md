# Locality-Sensitive-Hashing-Plagiarism-Detection

This program aims to find out the plagiarism in the set of available documents. These documents are submitted by the students for grading and a sample is collected to implement the algorithm. The submitted documents are compared with the original documents (Wikipedia Articles) and the degree of plagiarism (Directly copied, Light revision, heavy revision, non-plagiarism) can be detected. 

The algorithm used to detect plagiarized documents is Locality Sensitive Hashing. This technique hashes similar items into same bucket. The three steps involved in this algorithm are 
1. Shingling - Creating k-word shingles – For each document, k-word shingles are generated, and its corresponding ASCII values are stored. 

2. Min-Hashing -Generating Hash functions and Constructing Signature matrix – Different number of hash functions (L) are calculated using ax+b % N, where a,b are random integers, x is shingle index and N is the total number of unique k-shingles. With these hash functions, signature matrices of size L X C are created, where C is the number of documents in the sample/original documents folder.

The logic behind the construction of signature matrix can be found here: https://youtu.be/ZjdQD79Psi0


3. Locality Sensitive Hashing - Identifying plagiarized documents by hashing the documents into buckets.
The constructed signature matrix for the documents in sample folder is split into r rows and b bands. Each band is hashed into any one of the B buckets. Similarly, original document/s signature matrix is constructed and hashed into B buckets. Following this, candidate documents i.e., the documents that are hashed into same bucket as the original document for more than once are identified. False positives and false negatives are determined using jaccard similarity and a threshold value.

The results are optimized by splitting the signature matrix into different number of bands, rows and buckets for better results.

Finally, plagiarized documents are detected using LSH Algorithm in Python.
