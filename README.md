# longest-subsequence-
This algorithm is like search correction in youtube.whenever you search for something and make spelling mistake in typing this algorithm make that correct and search for that.
#number of total characters in D
def find_longest_subsequence_v1(S, D):
    """ Greedy Algorithm """
    d = sorted(D, key=len, reverse=True)
    for word in d:
        i = j = 0
        while True:
            try:
                i = S[i:].index(word[j]) + i
                j+=1
            except ValueError:
                break
            except IndexError:
                return word
#it can handle any type of input.               
S = "abppplee" 
D = {"able", "ale", "apple", "bale", "kangaroo"}

print(find_longest_subsequence_v1(S,D))
