# Sentiment-analysis-on-Text

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
        also Sequence of data is very important {RNN,LSTM etc}
        and also there will be both long and short term dependencies {LSTM}
        
  So we are using LSTM
   
  Procedure is
    -initially we should convert Text to Vector 
    Here we need to convert Text to numerical Features and there are many Techniques of converting it but Embeddeding is one 
    the best technique to use
    One Hot Encoding Vs Embedding
    In one Hot encoding if we have length of corpus 'n' which is very large then output will also be a vector of dimension       'n'.which is very hard for Neural Network to compute further and it doesnot take any Semantic Meaning into          consideration.so it is not recommended
    Instead we use Embedding layers where the output can any vector of dimension of our choice and it can learn as any other     weight paramater in Network during Back prop and it also take Semantic Meaning into consideration.
    
    
    
  
  
  
  
