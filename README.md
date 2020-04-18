# Sentiment Analysis On Text

IMDB-Internet Movie Database is owned by Amazon
 It contains lot of Data regarding the movies and their Review's data we use here is 
 ## Understanding Requirement
 Given a Review(Text) we need to determine whether it is positive or negative
 * 'Review': Text(Sequence of words)
 * 'Expression': Positive(0) or negative(1)
 so input is Review which is sequence of words
    output is 0 /1
 ## Data Agoisition && Data Preparation
 Fortunately kears provides us this dataset so it performs necessary Data cleaning,pre processing
 so now construct a Table which consists of word and frequency from the dataset Corpus(collection of all Documents or Reviews)
 and now sort them according to frequency in the decreasing order such that word which higher frequency is on top
 now select top 8000 word as there are most important and remove all other words from each of the Review or row or document
 ## Exploratory Data Analysis
 There is no need of Exploratory Data Analysis here.
 ## Modeling
  Here main point is it is Text data and Sequence of data is very important.so it is a Time series Problem
  i.e for Text data we prefer Neural Netorks {ANN,CNN,RNN,LSTM etc}
        also Sequence of data is very important and length of input is not same {RNN,LSTM etc}
        and also there will be both long and short term dependencies {LSTM}
        
  So we are using LSTM
   
  Procedure is
    --initially we should convert Text to Vector 
    Here we need to convert Text to numerical Features and there are many Techniques of converting it but Embeddeding is one 
    the best technique to use
    One Hot Encoding Vs Embedding
    In one Hot encoding if we have length of corpus 'n' which is very large then output will also be a vector of dimension       'n'.which is very hard for Neural Network to compute further and it doesnot take any Semantic Meaning into          consideration.so it is not recommended
    Instead we use Embedding layers where the output can any vector of dimension of our choice and it can learn as any other     weight paramater in Network during Back prop and it also take Semantic Meaning into consideration.
  -- Padding
     reviews x1=<x11,x12,x13,x14,x15.......x190>    length=90
             x2=<x21,x22,x23,x24.........x2100>      length=100
     so we are different length of reviews.Here the problem is when we are doing Back prop we need update weigths using 1          review at a time because of different lengths of review.so SGD of Batch size 1  need to used it is Very time consuming.
     here it is perfectly correct to do it but it is too slow
     But there is a Solution that if we make all the reviews to be of same length then we can batch them and send the              input.so this literally becomes SGD which batch Size 'k'.so it instantly becomes very fast while compare to previous one
     So we fix the Length of Reviews to be certain number and only take that may number of words into Network.if length is        less than we add "0" at the start of the Word Vector.
  --LSTM
    Same as we take multiple neurons in ANN.similarly in the real world we take multiple LSTM together in this problem I        took 200 and with 1 Hiiden layer.
    Also there are 2 types of Dropouts in LSTMS [HYPERPARAMETER]
      ---Input Dropout.
       --Recurrent Dropout.
    I took input dropout to be 0.2 and no recurrent dropout
    Finially with a sigmoid Layer to tell it is a positive or negative review
 ## Evaluation
  Here evaluation metric is Accuracy
  
  
  
  
