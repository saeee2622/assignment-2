import requests

url="https://samples.openweathermap.org/data/2.5/forecast/hourly?q=London,us&appid=b6907d289e10d714a6e88b30761fae22"



def getWeather_data(choice,date_time):
    res=requests.get(url)

    if res.status_code==200:
        data=res.json()

        if choice==1:
            for forecast in data['list']:
                if forecast['dt_txt']==date_time:
                    temp=forecast['main']['temp']
                    temp_c=round(temp-273.15) # converting kelvin to Celicus
                    print(f"Temperature at {date_time} : {temp_c}°C")
                    break
            else:
                print("No data available for that date and Time.....")
    
        elif choice==2:
            for forecast in data['list']:
                if forecast['dt_txt']==date_time:
                    print(f"Wind Speed at {date_time} : {forecast['wind']['speed']}")
                    break
            else:
                print("No data available for that date and Time.....")

        elif choice==3:
            for forecast in data['list']:
                if forecast['dt_txt']==date_time:
                    print(f"Pressure at {date_time} : {forecast['main']['pressure']}")
                    break
            else:
                print("No data available for that date and Time.....")

        else:
            print("Inavlid option .. please select a valid option..")

    else:
        print("Failed to retrive the data from rest api")




while True:
    print("0.Exit")
    print("1.Get Temperature")
    print("2.Get Wind Speed")
    print("3.Get Pressure")

    choice=int(input("Select any option : "))

    if choice==1:
        date_time=input("Enter the date and time format in following order : (YYYY-MM-DD HH:MM:SS) : ")
        getWeather_data(choice,date_time)

    elif choice==2:
        date_time=input("Enter the date and time format in following order : (YYYY-MM-DD HH:MM:SS) : ")
        getWeather_data(choice,date_time)

    elif choice==3:
        date_time=input("Enter the date and time format in following order : (YYYY-MM-DD HH:MM:SS) : ")
        getWeather_data(choice,date_time)

    elif choice==0:
        print("Exiting the program")
        break
           
    else:
        print("Invalid Choice.. Select a valid option ")
