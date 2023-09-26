while True:
   print("0.Exit")
   print("1.Get Temperature")
   print("2.Get Wind speed")
   print("3.Get Pressure")

   choice=int(input("select any option : "))

   if choice==1:
       date_time=input("Enter the date and the time format in following order : (YYYY-MM-DD HH:MM:SS) : ")
       getWeather_data(choice,date_time)
   elif choice==2:
      date_time=input("Enter the date and time format in the following order : (YYYY-MM-DD HH:MM:SS) : ")
      getWeather_data(choice,date_time)
   elif choice==3:
      date_time=input("Enter the date and time format in the following order : (YYYY-MM-DD HH:MM:SS) : ")
      getWeather_data(choice,date_time)
   elif choice==0:
        print("Existing the program")
        break
   else:
       print("invalid choice..select a valid option ")
      
