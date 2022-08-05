# giveaway_result_by_email

Tired of checking Ebit website to figure out if you're among the winners?
Set a cron job to run this script and receive the winners list by e-mail :)

## Getting started

>This is a simple webscraping using the classic beautiful soup lib. Then we steal the whole table of winners available in their [website](https://company.ebit.com.br/concorra-premios/ultimos-ganhadores), format the table using pretty_html_table lib and mail to you! 
    
<br>

## WHAT WE HAVE: 
<br>

![](https://imgur.com/mRq9SkD.png)


## WHAT WE WANT:  
<br>  
   
![](https://i.imgur.com/EIMs4x7.png)


   
## You'll need
- a gmail account 
- recent version of python installed
- clone this repository, browse into it
- execute `run.sh` (UNIX) OR `run.bat` (Windows)
- basic (VERY BASIC) knowledge of cron (or app deploy on heroku, it's up to you) - optional
     
 <br>
 <br>

# 1. Find where your python is
If you're using an unix based system, the command `which python3` must do the job for you:

![](https://i.imgur.com/xxFADqu.png)

If you're on Windows, the equivalent command is `where python3` OR `where python`.

so, this is the path where your python binary is located: */opt/homebrew/bin/python3*   

<br>
<br>


-----------------------   
# 2. Create an app password specially for this script  
We know you don't want to expose any password and, well, you can create infinite app passwords for your e-mail to use every single of them in a different app! Just follow [this](https://support.google.com/accounts/answer/185833?hl=en) AND GRAB YOUR 16 MAGIC CHARS for this script!  


<br>
<br>  

  -----------------------
# 3. Export as environment variable 
This handles how we authenticate with your super secret 16-digit password even if you're out of your beloved machine. If you are doing some deploy on Heroku, for example, the syntax to get the environment variables is exactly the same. If works on cron, works on your secret deploy. **The variables just have to be there!**   

`$ export EMAIL_PASSWORD=your16digitspassword`   
`$ export EMAIL_USERNAME=email@gmail.com`
  
This is the gmail credentials you'll use to authenticate **AND** to whom you'll send the table we've fetched from the website!
> if you wanna send the table to another person, change `receiver_email` directly on code   

<br>
<br>

  -----------------------  
# 4. Try to execute the raw script by typing on terminal 
`$ /opt/homebrew/bin/python3 scraping_winners.py`  
> ʕʘ̅͜ʘ̅ʔ remember, if the scraping_winners.py file is not on current directory, fill the absolute path to the .py file on command, just like we did with the interpreter python3 path!   

if the file successfully executes, this is what you'll get:   

![](https://i.imgur.com/XFOpUAD.png)

<br>
<br>

------
# 5. Check your mail!

<br>
<br>

-------
# 6. Take your cron! 
- On your terminal, type `$ crontable -e`  
- This will open a file, every line is potentially a task that you can schedule your computer to execute for you! In this case, we'll schedule a python file.  
- Translate your schedule to [cron syntax](https://crontab.guru/)
- To enable edition of the file, type `i` (yes, like insertion)
- Now, edit one line by following the example:
```
05 11 * * 5 /opt/homebrew/bin/python3  ~/Documents/scripts/scraping_winners.py
```
  
  This statement would execute the file scraping_winners.py file, located on Documents/scripts, using python3 interpreter, located at homebrew binaries folder every friday at 11h05

After settling your crontable file, type `Esc` to leave edition mode 

- `$ :wq` to write and quit the file
- you must see the output `crontab: installing new crontab`


<br>
<br>  

*ps: the file b4s.ipynb has nothing to do with the script, but I love jupyter since it's easier to manipulate tiny pieces of code;  the file you'll use to schedule your cron is the .py one*

## ✧･ﾟ: *✧･ﾟ:* ✧･ﾟ: *✧･ﾟ:* This is it. Suggestions? [Mail me](mailto:minhadona@tuta.io) ✧･ﾟ: *✧･ﾟ:* ✧･ﾟ: *✧･ﾟ:*

![](https://i.pinimg.com/originals/f4/e1/e0/f4e1e08ac2c429a6646892cbc265b5f2.gif)


