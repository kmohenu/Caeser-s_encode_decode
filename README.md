# Caeser-s_encode_decode
Caeser's cypher with  additional encoding and decoding for sentences
alphabet=("a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z")
# User ased to choose to "encode" or "decode"
encode_or_decode=input("please type encode or decode to select your choice: \n").lower()
# text of sentence to be encoded or decoded
orig_txt=input("Please input txt: \n").lower()
# Text sentence will be stripped of spaces
orig_txt=orig_txt.replace(" ","")
# jumps from (A-Z) to be used for encoding text
shift=int(input("Please input shift: \n"))

# Function to encode or decode text/sentence
def caeser(encode_or_decode,orig_txt,shift):
    
        placement=" "     
        for letter in orig_txt:
            
            if encode_or_decode == "encode":

                new_position=alphabet.index(letter) + shift
                new_position %= len(alphabet)
                placement+=alphabet[new_position]
                                
            elif encode_or_decode == "decode":
                new_position=alphabet.index(letter) - shift
                new_position %= len(alphabet)
                placement+=alphabet[new_position]
            else:
                 print("Your choices are encode or decode. Please try again.")
                 continue
    
        print(f" your {encode_or_decode}d text is:- {placement}")
                
            
    
caeser(encode_or_decode,orig_txt,shift)
