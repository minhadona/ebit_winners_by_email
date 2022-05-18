# giveaway_result_by_email

Tired of checking Ebit website to figure out if you're among the winners?
Set a cron job to run this script and receive the winners list by e-mail :)

## Getting started

>This is a simple webscraping using the classic beautiful soup lib. Then we steal the whole table of winners available in their [website](https://company.ebit.com.br/concorra-premios/ultimos-ganhadores), format the table using pretty_html_table lib and mail to you! 
    
   
# You'll need
- a gmail account 
- recent version of python installed
- basic knowledge of cron (or app deploy on heroku, it's up to you)
     
    
 -----------------------       
## 1. Find where your python is
If you're using an unix based system, the command `which python3` must do the job for you:

![](https://i.imgur.com/xxFADqu.png)

so, the path where your python bynary is locate is */opt/homebrew/bin/python3* 
    
    

-----------------------   
## 2. Create an app password specially for this script
We know you don't want to expose any password and then you might create infinite app passwords for your e-mail and use every single of them in one different app! Just follow [this](https://support.google.com/accounts/answer/185833?hl=en) AND GRAB YOUR 16 MAGIC CHARS!
  
    
      

  
  -----------------------
## 3. Export as user system variable 
This handles your super secret 16-digit password even if you're out of your beloved machine. If you'll doing some deploy on Heroku, for example, the syntax  to get the environment variables is exactly the same. If works on cron, works on your secret deploy.   

`$ export EMAIL_PASSWORD=this16digitspassword`   
`$ export EMAIL_USERNAME=email@gmail.com`
  
    
      
  
  -----------------------
## 4. Try to execute the raw script by typing on terminal 
`$ /opt/homebrew/bin/python3 b4s.py`  
:anger: remember, if the b4s.py file is not on current directoty, complete the absolte path on command, just like we did with the python3 path   
