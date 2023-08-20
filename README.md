# Tkinter_form
Basic Form using tkinter module 


    from tkinter import *

    root=Tk()
    root.geometry("500x344")
    
    def getVals():
        print("Submitting form")
        with open("record.txt","w") as file:
            file.write(f"Name: {nameval.get()}, Phone: {phoneVal.get()}, Gender: {genderVal.get()}, Emergency: {emergencyVal.get()}, PaymentMode: {paymentmodeVal.get()},"
                  f"CheckBox: {foodserviceVal.get()}\n")
    
    Label(root,text="Form",font="comicsansms 13 bold",pady=15).grid(row=0,column=5)
    # Text for a form
    name=Label(root,text="Name",pady=5)
    phone=Label(root,text="Phone",pady=5)
    gender=Label(root,text="Gender",pady=5)
    emergency=Label(root,text="Emergency",pady=5)
    paymentmode=Label(root,text="Payment Mode",pady=5)
    
    #Pack text for our form
    name.grid(row= 1,column=2)
    phone.grid(row= 2,column=2)
    gender.grid(row= 3,column=2)
    emergency.grid(row=4 ,column=2)
    paymentmode.grid(row=5 ,column=2)
    
    # thinker variable for storing entries
    nameval=StringVar()
    phoneVal=StringVar()
    genderVal=StringVar()
    emergencyVal=StringVar()
    paymentmodeVal=StringVar()
    foodserviceVal=IntVar()
    
    # Entry for a form
    nameeentry=Entry(root,textvariable=nameval)
    phoneeentry=Entry(root,textvariable=phoneVal)
    genderentry=Entry(root,textvariable=genderVal)
    emergencyentry=Entry(root,textvariable=emergencyVal)
    paymentmodeentry=Entry(root,textvariable=paymentmodeVal)
    
    # Packing the Entries
    nameeentry.grid(row=1 ,column=3)
    phoneeentry.grid(row= 2,column=3)
    genderentry.grid(row= 3,column=3)
    emergencyentry.grid(row= 4,column=3)
    paymentmodeentry.grid(row= 5,column=3)
    
    #checkbox & packing
    foodservice=Checkbutton(text="Click Me",variable=foodserviceVal)
    foodservice.grid(row=6,column=3,pady=10)
    
    # Button & Packing and assiging it a command
    Button(text="Submit",command=getVals).grid(row=8,column=2)
    
    
    
    root.mainloop()
