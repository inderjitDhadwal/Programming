<h1>Python Programming Project</h1>

#To work with APIs in python, we can use the request modules 
import requests

#defining Function so whenfuction is called control will direct to this part.
def askadvice():

   #assigning URL to the request_url Variable
   request_url = "https://api.adviceslip.com/advice"
   #Get data from web API
   response = requests.get(request_url)

   #to convert into json object into a python friendly format
   data = response.json()
  

   #ask user input
   ans = input("you want to hear advice(yes or no) ? ")
  

   # check answer of user if yes if statement will run 
   #ortherwise the else statement
   if ans == "yes" :
     print(data["slip"]["advice"])
     
   else :
     
      # Contain othet if statement in else statement if its 
      #true message will 
      #apper otherwise inner else will execute.
     
    if ans == "no":
      print("Alright! try again")
     
    else:

      #if user entered wrong input it will display message and 
      #ask again if user want to hear advice 
      print("Oops ! you have entered wrong try again ")

      #calling Function
      askadvice()
      
     

#to find error in program if there is error in the main      #program error handling is used. 
try:
  
  #Calling Function
  askadvice()

#If there is error in try block, instead of try block, except 
#block message will be display
except Exception as e:
  
  print ("Sorry there is problem in the program ")
  print (e)

#This message will print when the program end.
print ("Thank you !")
