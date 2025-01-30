# how to transfer files from wsl to windows?

i created a `.csv` file in the [data preparation tutorial page](https://zeeamini.com/data_preparation.html) and now i want to transfer it to windows. 

why? because i want to open it on windows and also want to have it on my computer for any reason.

i have created my file in my home directory, so i need to be in my home directory while running the command:

![linux directory path](https://github.com/user-attachments/assets/ce26c0e0-5964-4c87-97d2-f9f013f59584)

then you would say: copy it from this location (the path of your file in wsl) to that location (the path to your windows folder).

```bash
cp /home/zeta/data_preparation.csv /mnt/c/Users/Zeta/Downloads
```

adjust the username or file names to match yours.

![linux directory path](https://github.com/user-attachments/assets/4dca1f7a-8af3-4db8-b691-4ad4ca6b2863)

it is now located in my downloads.

# second method

if for some reason you prefer not to use the terminal, you can find the file on linux directly from your computer because wsl is essentially inside the windows environment.

you can click on it and find your way through home, username, and the `.csv` file. 

![wsl](https://github.com/user-attachments/assets/2a397c63-4255-4426-bd64-63a44951dc30)





















