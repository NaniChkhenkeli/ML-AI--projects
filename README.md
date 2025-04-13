../hw0 solution descriptions are provided in the project files. 

## ../hw1 ##
minesweeper
project implements ai agent that can play the classic game of minesweeper using propositional logic and fnowledge-based reasoning. 
 player must identify all the mines on a grid without clicking on them. ai uses  logical reasoning to determine which cells are safe to click and which cells are likely to contain mines.

 how works:
 AI starts with no knowledge about the bpard. 
 makes ramdon move. 
 when a safe cell is clicked, ai learns number of neighboring mines and updates its knowledge base. 
 ai uses logical inference to deduce which cells are safe and which are mines:
   if sentence has count of 0, all cells are safe.
   if sentence has count equal to number of cells, all its cells are mines. 
   if one sentence is subset of another, diff can form new sentence. 
 ai wins if identifies all mines. loses if clicks on a mine. 
 
 sentence class 
  known_mines: Returns the set of cells that are definitely mines.
  known_safes: Returns the set of cells that are definitely safe.
  mark_mine: Updates the sentence when a cell is confirmed to be a mine.
  mark_safe: Updates the sentence when a cell is confirmed to be safe.
  
  minesweeperai class 
moves_made: cells that have already been clicked.
mines: cells known to be mines.
safes: cells known to be safe.
knowledge: list of logical sentences representing the AI's knowledge.

key methods in this class are:
add_knowledge: updates the ai's knowledge base with new information about a cell and its neighboring mines.
make_safe_move: returns a safe cell to click.
make_random_move: returns a random cell to click when no safe moves are available.

knights

this project slves logic puzzle and uses logical sentences to represent statement made by characters and determines who is knight or knave. 

 how works:
 each character (A, B, C) is represented by two symbols: knight (truth-teller) and knave (liar).
 ex: AKnight means "A is a Knight," and AKnave means "A is a Knave."
 statements made by characters are translated into logical sentences using And, Or, Implication, and Biconditional.
 ex: If A says, "I am a Knight," this is represented as:
 biconditional(AKnight, AKnight)
 model_check function checks all possible combinations of truth assignments to determine which symbols are consistent with the knowledge base.
 
puzzles

puzzle 0:
A says i am both knight and knave. so A must be a Knave because statement is contradiction. 
puzzle 1: 
A says we are both knaves. so if A is knight, statement true, but knights cant lie. => A is knave. -> st false -> B knight. 
puzzle 2: 
A says we are same kind. B says we are different. if A is knight, B must be knight, B's st shold be false, thats inpossible. => A knave, B knight.
puzzle 3:
A says either i am knight or i am knave. => true, A is knight. 
B says i am knave, c is knave. => B's st are contradictory, so B is knave. 
C says A is knight. => true, c is knight. 

## ..\hw2\ ##

PageRank algorithm. (sampling + iterative calculation)

for this project we needed to work on transition_model, sample_pagerank, iterate_pagerank.py files. 
first step is to sparse directory of HTML files to create represenation of web pages and their links.
then function need each html file, extracts links using regular expression and stores them in dictionary. 
transition_model calculates probability distribution of which page a random surfer would visit next,given the current page and damping vector. it considers both the links from the current page and the overall corpus, ensuring that probabilities sum to 1.
sample_pagerank function estimates pagerank by simulating random surfer for a specified number of samples. it tracks how often each page is visited and normalizes these counts to derive pagerank values. 
iterative_pagerank function computes pagerank values iteratively, updating them based on contributions from linking pages until the values converge. 


heredity.py

joint_probability function calculates joint probability of the specified gene and trait distributions for all individuals on the family.  if considers if each person has 0,1,2 copies of the gene and if they exhibit the trait, taking into account parental inheritance and mutation probabilities.

update function updates probabilities dictionary with newly computed joint probability. adds p to the appropriate gene and trait ditributions for each person beased on their status in one, two, have_genes. 

normalize function normalizes probability distributions for each person so that they sum to 1. it ensures relative proprrtions of the prob remain the same after normalization. 


## ..\hw3\ ##
enforce_node_consistency: removes words that dont match length requirements. filters each variable's domain to only keep words of correct length. 
revise&ac3:revise removes words from x's domain that have no matching words in y's domain at overlap. ac3() uses queue of arcs to enforce consistency across all variables. goes through constraints until no more revisions needed. 
backtracking search: choses next variable using MRV and degree heuristics. orders values by lleast constraining first. then recursively tries asiignments with inference. 
F.EX.
2 letters horizontally, 2 vertically, overlap(1,1). -> remove all words not of length 2 from domains, ensure horizontal and vertical words agree at overlap, if "at" horizontal, vertical must start from T. contineus until valid solution found or all possibilities exhausted.


## ..\hw4\ ##
Nim project with AI's turn :
game starts eith 4 piles [1,3,5,7]. player and AI take truns removing any number of sticks from a single pile. AI uses trained Q-learning model to choose optimal moves based on state-action values, after each turn algorithm checks if all piles are empty. if yes -> last player to make a move wins, that is notmal win; 
what i added: training loop to let AI learn optimal strategies, also check for valid pile and count before accepting user input, also game over check and AI move function that chooses the best move using learned Q-values.

shopping project :
loads dataset, converts features, maps months to numbers, encodes labels. splits data 60-40, tracks K-Nearest neighbors classifier using scikit-learn, predicts on test and compares with true labels. predicts on test and compares with true labels. 
what I added: data preprocessing, label encoding, model training using KNN(k=1), ecaluation function for sensitivity and specificity. 


## ..\hw4\ ##
project: traffic TensorFlow with GTSRB dataset 
build AI model to classify German traffic signs, dataset contains 43 different images of roag signs, 
what i added : load_data function (loads, reads, resizes, stores each image and its label), 
get_model (defines CNN using TensorFlow Keras, model includes convolutional layers with ReLU activation, max-pooling layers, dropout layers, final softmax output layer with 43 units, method is compiled with categorical crossentroy loss and Adam optimizer. 
also added training and evaluation, trained for 10 epochs, after training the model is evaluated on the test to check accuracy <3
