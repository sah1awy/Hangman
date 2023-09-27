import random
HANGMAN = ['_____',
          '|    |',
          '|    o',
          '|    |',
          '|   /|\ ',
          '|    |',
          '|   / \ ']
word = ["python", "android","andromeda","antidote"]

class Hangman:
  def __init__(self,w):
    self.word_to_guess = w
    self.failed_attempts = 0
    self.game_progress = list('_' * len(HANGMAN))
  
  def get_input(self):
    i = input("Enter a letter:")
    return i
  def is_invalid(self,w):
    return w.isdigit() or w.isalpha() and len(w) > 1
  
  def game_status(self):
    print("\n")
    print("\n".join(HANGMAN[:self.failed_attempts]))
    print("\n")
    print(" ".join(self.game_progress))  
  def find_indexes(self,x):
    return[i for i,c in enumerate(self.word_to_guess) if c==x]
  
  def game_update(self,indexes,l):
    for i in indexes:
      self.game_progress[i] = l

  def play(self):
    while len(HANGMAN) >= self.failed_attempts: #  1 2 3 4 5 6 7 
      self.game_status()
      if self.failed_attempts == len(HANGMAN):
        break
      x = self.get_input()
      if self.is_invalid(x):
        print("Invalid input")
        continue
      if x in self.game_progress:
        print("already entered try another letter")
        continue
      if x in self.word_to_guess:
        indexes = self.find_indexes(x)
        self.game_update(indexes,x)
        if self.game_progress.count('_') == 0:
          print("You win")
          print(f"the word is:{self.word_to_guess}")
          return
      else:
        self.failed_attempts += 1  
    print("you lost")
  
r = random.choice(word)
o = Hangman(r)
o.play()
