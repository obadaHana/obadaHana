import pickle


# Reciving the dicinary and the the file name to the funcion
def create_file(developers, filename):
    
    with open(filename, 'wb') as out_file:
        pickle.dump (developers,out_file)

        
def read_file(filename):
    with open(filename, 'rb') as in_file:
        return pickle.load(in_file)

def display_bug_count (developers, target):
    if target in developers:
        print(f'(target) has introduced (developers{target}) bugs. ')
        

def main():
    try:
        #Creating a dicinary
        developers = {
        'Anna': 5,
        'Kalle': 6,
        'Max': 7,}
        print (developers)        
        #creating a string with file name
        filename = 'developers.dat'
        #sending the dicinary and the the file name to the funcion
        create_file(developers, filename)
        #        
        developers = read_file(filename)
        display_bug_count (developers, 'Annaa')
    except FileNotFoundError:
        print('ERROR: The specified file does not exist')
