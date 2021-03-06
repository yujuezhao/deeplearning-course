### Recurrent Neural Networks

1. Suppose your training examples are sentences (sequences of words). Which of the following refers to the $j^{th}$ word in the $i^{th}$ training example?

   > $x^{(i)<j>}$

2. Consider this RNN: 

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/1.PNG' width='80%'>

   This specific type of architecture is appropriate when

   > $T_x=T_y$

3. To which of these tasks would you apply a many-to-one RNN architecture? (Check all that apply).

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/2.PNG' width='60%'>

   > * Sentiment classification (input a piece of text and output a 0/1 to denote positive or negative sentiment)
   > * Gender recognition from speech (input an audio clip and output a label indicating the speaker’s gender)

4. You are training this RNN language model.

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/3.PNG' width='60%'>

   At the $t^{th}$ time step, what is the RNN doing? Choose the best answer.

   > Estimating $P(y^{<t>} | y^{<1>}, y^{<2>}, …, y^{<t-1>})$

5. You have finished training a language model RNN and are using it to sample random sentences, as follows:

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/4.PNG' width='80%'>

   What are you doing at each time step t?

   > (i) Use the probabilities output by the RNN to **randomly sample** a chosen word for that time-step as ${y}^{<t>}$. 
   >
   > (ii) Then pass this **selected word** to the next time-step.

6. You are training an RNN, and find that your weights and activations are all taking on the value of `NaN` (“Not a Number”). Which of these is the most likely cause of this problem?

   > Exploding gradient problem.

7. Suppose you are training a LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations $a^{<t>}$. What is the dimension of $Γ_u​$ at each time step?

   > 100
   > $$
   > a^{<t>}=g\left(\underbrace{{W}_{a a}}_{(100,100)} \underbrace{a^{<t-1>}}_{(100,1)}+\underbrace{W_{a x}}_{(100,10000)}\underbrace{x^{<t>}}_{(10000,1)}+b_{a} \right)\\
   > $$
   >
   > $$
   > \Gamma_{u}=\sigma\left(W_{u}\left[a^{<t-1>}, x^{<t>}\right]+b_{u}\right)
   > $$

8.  Here’re the update equations for the GRU

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/5.PNG' width='40%'>

   Alice proposes to simplify the GRU by always removing the $\Gamma_{u} .$ l.e., setting $\Gamma_{u}=1$. Betty proposes to simplify the GRU by removing the $\Gamma_{r} .$ I. e., setting $\Gamma_{r}=1$
   always. Which of these models is more likely to work without vanishing gradient
   problems even when trained on very long input sequences?

   > Betty’s model (removing $Γ_r$), because if $Γ_u ≈ 0$ for a timestep, the gradient can propagate back through that timestep without much decay.

9. Here are the equations for the GRU and the LSTM:

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/02_programming-assignments/images/6.PNG'>

   From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to _______ and ______ in the GRU. What should go in the the blanks?

   > $Γ_u$ and $1-Γ_u$

10. You have a pet dog whose mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as $x^{<1>}, …, x^{<365>}$. You’ve also collected data on your dog’s mood, which you represent as $y^{<1>}, …, y^{<365>}$. You’d like to build a model to map from $x \rightarrow y$. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

    > Unidirectional RNN, because the value of $y^{<t>}$ depends only on $x^{<1>}, …, x^{<t>}$, but not on $x^{<t+1>}, …, x^{<365>}$

