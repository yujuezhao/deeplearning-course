### Natural Language Processing & Word Embeddings

1. Suppose you learn a word embedding for a vocabulary of 10000 words. Then the embedding vectors should be 10000 dimensional, so as to capture the full range of variation and meaning in those words.

   > False

2. What is t-SNE?

   >   A non-linear dimensionality reduction technique

3. Suppose you download a pre-trained word embedding which has been trained on a huge corpus of text. You then use this word embedding to train an RNN for a language task of recognizing if someone is happy from a short snippet of text, using a small training set.

   | x (input text)               | y (happy?) |
   | ---------------------------- | ---------- |
   | I'm feeling wonderful today! | 1          |
   | I'm bummed my cat is ill.    | 0          |
   | Really enjoying this!        | 1          |

   > True

4. Which of these equations do you think should hold for a good word embedding? (Check all that apply)

   > $e_{boy} - e_{girl} ≈ e_{brother} - e_{sister}$
   >
   > $e_{boy} - e_{brother} ≈ e_{girl} - e_{sister}$

5.  Let E be an embedding matrix, and let $o_{1234}$ be a one-hot vector corresponding to word 1234. Then to get the embedding of word 1234, why don’t we call $E∗o_{1234}$ in Python?

   > It is computationally wasteful.

6.  When learning word embeddings, we create an artificial task of estimating $P(target \mid context)$. It is okay if we do poorly on this artificial prediction task; the more important by-product of this task is that we learn a useful set of word embeddings.  

   > True

7. In the **word2vec** algorithm, you estimate $P(t \mid c)$, where t is the target word and c is a context word. How are t and c chosen from the training set? Pick the best answer.

   > c and t are chosen to be **nearby words**.

8.  Suppose you have a 10000 word vocabulary, and are learning 500-dimensional word embeddings. The word2vec model uses the following softmax function:
   $$
   P(t∣c)=\frac {e^{θ^T_te_c}}{∑^{10000}_{t′=1}e^{θ^T_{t′}e_c}}
   $$
   Which of these statements are correct? Check all that apply.

   > - [x] $θ_t$ and $e_c $are both 500 dimensional vectors.
   >
   > - [x] $θ_t$ and $e_c$ are both trained with an optimization algorithm such as Adam or gradient descent.
   >
   > - [ ] After training, we should expect $\theta_{t}$ to be very close to $e_{c}$ when $t$ and $c$ are the same word.

9. Suppose you have a 10000 word vocabulary, and are learning 500-dimensional word embeddings.The GloVe model minimizes this objective:
   $$
   \min \sum_{i=1}^{10,000} \sum_{j=1}^{10,000} f\left(X_{i j}\right)\left(\theta_{i}^{T} e_{j}+b_{i}+b_{j}^{\prime}-\log X_{i j}\right)^{2}
   $$
   Which of these statements are correct? Check all that apply.

   > * $θ_i$ and $e_j$ should be initialized randomly at the beginning of training.
   > * $X_{ij}$ is the number of times word i appears in the context of word j.
   > * The weighting function $f(.)$ must satisfy $f(0) = 0$.

10. You have trained word embeddings using a text dataset of m1 words. You are considering using these word embeddings for a language task, for which you have a separate labeled dataset of m2 words. Keeping in mind that using word embeddings is a form of transfer learning, under which of these circumstance would you expect the word embeddings to be helpful?

    > m1 >> m2

