# giveaway_result_by_email

Tired of checking Ebit website to figure out if you're among the winners?
Set a cron job to run this script and receive the winners list by e-mail :)

## Getting started

>This is a simple webscraping using the classic beautiful soup lib. Then we steal the whole table of winners available in their [website](https://company.ebit.com.br/concorra-premios/ultimos-ganhadores), format the table using pretty_html_table lib and mail to you! 
    
   
# You'll need
- a gmail account 
- recent version of python installed
- basic knowledge of cron (or app deploy on heroku, it's up to you)
     
         
## 1. Find where your python is
If you're using an unix based system, the command `which python3` must do the job for you:

![](https://i.imgur.com/xxFADqu.png)

so, the path where your python bynary is locate is */opt/homebrew/bin/python3*   

<br>
<br>


-----------------------   
## 2. Create an app password specially for this script  
We know you don't want to expose any password and then you might create infinite app passwords for your e-mail and use every single of them in one different app! Just follow [this](https://support.google.com/accounts/answer/185833?hl=en) AND GRAB YOUR 16 MAGIC CHARS!  


<br>
<br>  

  -----------------------
## 3. Export as environment variable 
This handles your super secret 16-digit password even if you're out of your beloved machine. If you are doing some deploy on Heroku, for example, the syntax to get the environment variables is exactly the same. If works on cron, works on your secret deploy. The variables just have to be there!  

`$ export EMAIL_PASSWORD=this16digitspassword`   
`$ export EMAIL_USERNAME=email@gmail.com`
  
This is the gmail you'll use to authenticate **and** to where you'll send the table we've fetched from the website!
> if you wanna send the table to another person, change `receiver_email` directly on code   

<br>
<br>

  -----------------------  
## 4. Try to execute the raw script by typing on terminal 
`$ /opt/homebrew/bin/python3 b4s.py`  
> ʕʘ̅͜ʘ̅ʔ remember, if the b4s.py file is not on current directory, fill the absolute path to the .py file on command, just like we did with the interpreter python3 path!   

<br>
<br>

------
## 5. Check your mail!
Something like this must be there:  

![](https://i.imgur.com/EIMs4x7.png)

The original table comes from: 

![](https://imgur.com/mRq9SkD.png)

<br>
<br>

-------
## 6. Take your cron! 
- On your terminal, type `$ crontable -e`  
- This will open a file, every line is potentially a task that you can schedule your computer to execute for you! In this case, we'll schedule a python file.  
- Translate your schedule to [cron syntax](https://crontab.guru/)
- To habilitate edition, type `i` (yes, like insertion)
- Now, edit one line by following the example:
```
05 11 * * 5 /opt/homebrew/bin/python3  ~/Documents/scripts/b4s.py
```
  
  This would execute the file b4s.py file, located on Documents/scripts, using python3 interpreter, located at homebrew binaries folder every friday at 11h05

- `$ Esc`
- `$ :wq` to write and quit the file
- you must see the output `crontab: installing new crontab`


<br>
<br>  

## ✧･ﾟ: *✧･ﾟ:* ✧･ﾟ: *✧･ﾟ:* This is it. Suggestions? [Mail me](mailto:minhadona@tuta.io) ✧･ﾟ: *✧･ﾟ:* ✧･ﾟ: *✧･ﾟ:*
![](https://i.pinimg.com/originals/f4/e1/e0/f4e1e08ac2c429a6646892cbc265b5f2.gif)


