# ProjetoFinal
Código do Projeto Final de ESOF



# -*- coding: cp1252 -*-
from Tkinter import *
import random
import time;
import datetime

root = Tk()
root.geometry("1350x750+0+0")
root.title("Cardápio Digital")
root.configure(background='black')

Tops=Frame(root,width=1350,height=100, bd=14,relief="raise")
Tops.pack(side=TOP)

f1=Frame(root,width=900,height=650, bd=8,relief="raise")
f1.pack(side=LEFT)

f2=Frame(root,width=440,height=650, bd=8,relief="raise")
f2.pack(side=RIGHT)

f1a= Frame(f1,width=900,height=330, bd=8,relief="raise")
f1a.pack(side=TOP)

f2a= Frame(f1,width=900,height=320, bd=6,relief="raise")
f2a.pack(side=BOTTOM)

ft2=Frame(f2,width=440,height=450, bd=12,relief="raise")
ft2.pack(side=TOP)
fb2=Frame(f2,width=440,height=250, bd=16,relief="raise")
fb2.pack(side=BOTTOM)

f1aa= Frame(f1a,width=400,height=330, bd=16,relief="raise")
f1aa.pack(side=LEFT)
f1ab= Frame(f1a,width=400,height=330, bd=16,relief="raise")
f1ab.pack(side=RIGHT)

f2aa= Frame(f2a,width=450,height=330, bd=14,relief="raise")
f2aa.pack(side=LEFT)

f2ab= Frame(f2a,width=450,height=330, bd=14,relief="raise")
f2ab.pack(side=RIGHT)

Tops.configure(background='black')
f1.configure(background='black')
f2.configure(background='black')

lblInfo=Label(Tops,font=('amaranth',70,'bold'),text=" Sistema de Cardápio\t", bd=10)
lblInfo.grid(row=0,column=0)
#============================Method==================#
def Receipt():
    txtReceipt.delete("1.0",END)
    x=random.randint(110908,500876)
    randomRef=str(x);
    Receipt_Ref.set("PAGAMENTO "+randomRef)
    txtReceipt.insert(END,'Pedidos Red:\t\t\t' + Receipt_Ref.get()+'\t\t' + DateofOrder.get()+"\n")
    txtReceipt.insert(END,'Itens \t\t\t\t\t' + "Custo dos Itens \n\n")
    txtReceipt.insert(END,'Latta\t\t\t\t\t'+ E_Latta.get()+"\n");
    txtReceipt.insert(END,'Espresso\t\t\t\t\t'+E_Espresso.get()+"\n")
    txtReceipt.insert(END,'Café Gelado \t\t\t\t\t' +E_Iced_Latta.get()+"\n")
    txtReceipt.insert(END,'Café do Vale \t\t\t\t\t' + E_Vale_Coffee.get()+"\n");
    txtReceipt.insert(END,'Cappuccino \t\t\t\t\t' + E_Cappuccino.get()+"\n")
    txtReceipt.insert(END, 'Café Africano \t\t\t\t\t' + E_African_Coffee.get()+"\n")
    txtReceipt.insert(END, 'Café Americano \t\t\t\t\t' + E_American_Coffee.get()+"\n")
    txtReceipt.insert(END, 'Cappuccino Gelado \t\t\t\t\t' + E_Iced_Cappuccino.get()+"\n")
    txtReceipt.insert(END, 'Bolo de Café \t\t\t\t\t' + E_Coffee_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo Red Velvet \t\t\t\t\t' + E_Red_Velvet_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo Nega Maluca \t\t\t\t\t' + E_Black_Forest_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo de Limão \t\t\t\t\t' + E_Boston_Cream_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo de Leite Ninho \t\t\t\t\t' + E_Lagos_Chocolate_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo de Nutella \t\t\t\t\t' + E_Kilburn_Chocolate_Cake.get()+"\n")
    txtReceipt.insert(END, 'Bolo de Nozes \t\t\t\t\t' + E_Carlton_Hill_Cake.get()+"\n")
    txtReceipt.insert(END, 'Donuts \t\t\t\t\t' + E_Queen_Dark_Cake.get()+"\n")
    txtReceipt.insert(END, 'Preço das Bebidas \t\t' + CostofDrinks.get()+'\t Taxas: \t\t'+PaidTax.get()+"\n")
    txtReceipt.insert(END, 'Preço das Comidas \t\t' + CostofCakes.get()+ '\t SubTotal:\t\t' +SubTotal.get()+"\n")
    txtReceipt.insert(END, 'Taxa de Serviço \t\t' + ServiceCharge.get()+ '\t Total:\t\t' + TotalCost.get()+"\n")
    
def CostOfItem():
    Item1=float(E_Latta.get())
    Item2=float(E_Espresso.get())
    Item3=float(E_Iced_Latta.get())
    Item4=float(E_Vale_Coffee.get())
    Item5=float(E_Cappuccino.get())
    Item6=float(E_African_Coffee.get())
    Item7=float(E_American_Coffee.get())
    Item8=float(E_Iced_Cappuccino.get())
    Item9=float(E_Coffee_Cake.get())
    Item10=float(E_Red_Velvet_Cake.get())
    Item11=float(E_Black_Forest_Cake.get())
    Item12=float(E_Boston_Cream_Cake.get())
    Item13=float(E_Lagos_Chocolate_Cake.get())
    Item14=float(E_Kilburn_Chocolate_Cake.get())
    Item15=float(E_Carlton_Hill_Cake.get())
    Item16=float(E_Queen_Dark_Cake.get())

    PriceofDrinks=(Item1*1.2)+(Item2*1.99)+(Item3*2.05)+(Item4*1.89)+(Item5*1.99)+(Item6*2.99)+(Item7*2.39)+(Item8*1.29)
    PriceofCakes=(Item9*1.35)+(Item10*2.2)+(Item11*1.99)+(Item12*1.49)+(Item13*1.8)+(Item14*1.67)+(Item15*1.6)+(Item16*1.99)

    DrinksPrice="R$",str('%.2f'%(PriceofDrinks))
    CakesPrice="R$",str('%.2f'%(PriceofCakes))
    CostofCakes.set(CakesPrice)
    CostofDrinks.set(DrinksPrice)
    SC="R$",str('%.2f'%(1.59))
    ServiceCharge.set(SC)

    SubTotalofITEMS="R$",str('%.2f'%(PriceofDrinks+PriceofCakes+1.59))
    SubTotal.set(SubTotalofITEMS)

    Tax="R$",str('%.2f'%((PriceofCakes+PriceofDrinks+1.59)*0.15))
    PaidTax.set(Tax)
    TT=((PriceofDrinks+PriceofCakes+1.59)*0.15)
    TC="R$",str('%.2f'%(PriceofDrinks+PriceofCakes+1.59+TT))
    TotalCost.set(TC)
#=====================================================================================



def qExit():
    qExit = messagebox.askyesno("Quit System" ," Você deseja sair do aplicativo?")
    if qExit>0:
        root.destroy()
        return

def Reset():
    PaidTax.set("")
    SubTotal.set("")
    TotalCost.set("")
    CostofDrinks.set("")
    CostofCakes.set("")
    ServiceCharge.set("")
    txtReceipt.delete("1.0",END)
    E_Latta.set("0")
    E_Espresso.set("0")
    E_Iced_Latta.set("0")
    E_Vale_Coffee.set("0")
    E_Cappuccino.set("0")
    E_African_Coffee.set("0")
    E_American_Coffee.set("0")
    E_Iced_Cappuccino.set("0")

    E_Coffee_Cake.set("0")
    E_Red_Velvet_Cake.set("0")
    E_Black_Forest_Cake.set("0")
    E_Boston_Cream_Cake.set("0")
    E_Lagos_Chocolate_Cake.set("0")
    E_Kilburn_Chocolate_Cake.set("0")
    E_Carlton_Hill_Cake.set("0")
    E_Queen_Dark_Cake.set("0")

#=================
    var1.set(0)
    var2.set(0)
    var3.set(0)
    var4.set(0)
    var5.set(0)
    var6.set(0)
    var7.set(0)
    var8.set(0)
    var9.set(0)
    var10.set(0)
    var11.set(0)
    var12.set(0)
    var13.set(0)
    var14.set(0)
    var15.set(0)
    var16.set(0)
    txtLatta.configure(state=DISABLED)
    txtEspresso.configure(state=DISABLED)
    txtIced_Latta.configure(state=DISABLED)
    txtVale_Coffee.configure(state=DISABLED)
    txtCappuccino.configure(state=DISABLED)
    txtAfrican_Coffee.configure(state=DISABLED)
    txtAmerican_Coffee.configure(state=DISABLED)
    txtIced_Cappuccino.configure(state=DISABLED)
    txtCoffee_Cake.configure(state=DISABLED)
    txtRed_Velvet_Cake.configure(state=DISABLED)
    txtBlack_Forest_Cake.configure(state=DISABLED)
    txtBoston_Cream_Cake.configure(state=DISABLED)
    txtLagos_Chocolate_Cake.configure(state=DISABLED)
    txtKilburn_Chocolate_Cake.configure(state=DISABLED)
    txtCarlton_Hill_Cake.configure(state=DISABLED)
    txtQueen_Dark_Cake.configure(state=DISABLED)


    #============================Variables==================#
var1=IntVar()
var2=IntVar()
var3=IntVar()
var4=IntVar()
var5=IntVar()
var6=IntVar()
var7=IntVar()
var8=IntVar()
var9=IntVar()
var10=IntVar()
var11=IntVar()
var12=IntVar()
var13=IntVar()
var14=IntVar()
var15=IntVar()
var16=IntVar()

DateofOrder=StringVar()
Receipt_Ref=StringVar()
PaidTax=StringVar()
SubTotal=StringVar()
TotalCost=StringVar()
CostofCakes=StringVar()
CostofDrinks=StringVar()
ServiceCharge=StringVar()

E_Latta=StringVar();
E_Espresso=StringVar()
E_Iced_Latta=StringVar()
E_Vale_Coffee=StringVar()
E_Cappuccino=StringVar()
E_African_Coffee=StringVar()
E_American_Coffee=StringVar()
E_Iced_Cappuccino=StringVar()

E_Coffee_Cake=StringVar()
E_Red_Velvet_Cake=StringVar()
E_Black_Forest_Cake=StringVar()
E_Boston_Cream_Cake=StringVar()
E_Lagos_Chocolate_Cake=StringVar()
E_Kilburn_Chocolate_Cake=StringVar()
E_Carlton_Hill_Cake=StringVar()
E_Queen_Dark_Cake=StringVar()

E_Latta.set("0")
E_Espresso.set("0")
E_Iced_Latta.set("0")
E_Vale_Coffee.set("0")
E_Cappuccino.set("0")
E_African_Coffee.set("0")
E_American_Coffee.set("0")
E_Iced_Cappuccino.set("0")

E_Coffee_Cake.set("0")
E_Red_Velvet_Cake.set("0")
E_Black_Forest_Cake.set("0")
E_Boston_Cream_Cake.set("0")
E_Lagos_Chocolate_Cake.set("0")
E_Kilburn_Chocolate_Cake.set("0")
E_Carlton_Hill_Cake.set("0")
E_Queen_Dark_Cake.set("0")

#====================================================================
def chkbutton_value():
    if(var1.get()==1):
        txtLatta.configure(state=NORMAL)
    elif var1.get()==0:
        txtLatta.configure(state=DISABLED)
        E_Latta.set("0")
    if(var2.get()==1):
        txtEspresso.configure(state=NORMAL)
    elif var2.get()==0:
        txtEspresso.configure(state=DISABLED)
        E_Espresso.set("0")
    if(var3.get()==1):
        txtIced_Latta.configure(state=NORMAL)
    elif var3.get()==0:
        txtIced_Latta.configure(state=DISABLED)
        E_Iced_Latta.set("0")
    if(var4.get()==1):
        txtVale_Coffee.configure(state=NORMAL)
    elif var4.get()==0:
        txtVale_Coffee.configure(state=DISABLED)
        E_Vale_Coffee.set("0")
    if(var5.get()==1):
        txtCappuccino.configure(state=NORMAL)
    elif var5.get()==0:
        txtCappuccino.configure(state=DISABLED)
        E_Cappuccino.set("0")
    if(var6.get()==1):
        txtAfrican_Coffee.configure(state=NORMAL)
    elif var6.get()==0:
        txtAfrican_Coffee.configure(state=DISABLED)
        E_African_Coffee.set("0")
    if(var7.get()==1):
        txtAmerican_Coffee.configure(state=NORMAL)
    elif var7.get()==0:
        txtAmerican_Coffee.configure(state=DISABLED)
        E_American_Coffee.set("0")
    if(var8.get()==1):
        txtIced_Cappuccino.configure(state=NORMAL)
    elif var8.get()==0:
        txtIced_Cappuccino.configure(state=DISABLED)
        E_Iced_Cappuccino.set("0")
    if(var9.get()==1):
        txtCoffee_Cake.configure(state=NORMAL)
    elif var9.get()==0:
        txtCoffee_Cake.configure(state=DISABLED)
        E_Coffee_Cake.set("0")
    if(var10.get()==1):
        txtRed_Velvet_Cake.configure(state=NORMAL)
    elif var10.get()==0:
        txtRed_Velvet_Cake.configure(state=DISABLED)
        E_Red_Velvet_Cake.set("0")
    if(var11.get()==1):
        txtBlack_Forest_Cake.configure(state=NORMAL)
    elif var11.get()==0:
        txtBlack_Forest_Cake.configure(state=DISABLED)
        E_Black_Forest_Cake.set("0")
    if(var12.get()==1):
        txtBoston_Cream_Cake.configure(state=NORMAL)
    elif var12.get()==0:
        txtBoston_Cream_Cake.configure(state=DISABLED)
        E_Boston_Cream_Cake.set("0")
    if(var13.get()==1):
        txtLagos_Chocolate_Cake.configure(state=NORMAL)
    elif var13.get()==0:
        txtLagos_Chocolate_Cake.configure(state=DISABLED)
        E_Lagos_Chocolate_Cake.set("0")
    if(var14.get()==1):
        txtKilburn_Chocolate_Cake.configure(state=NORMAL)
    elif var14.get()==0:
        txtKilburn_Chocolate_Cake.configure(state=DISABLED)
        E_Kilburn_Chocolate_Cake.set("0")
    if(var15.get()==1):
        txtKilburn_Chocolate_Cake.configure(state=NORMAL)
    elif var15.get()==0:
        txtCarlton_Hill_Cake .configure(state=DISABLED)
        E_Carlton_Hill_Cake .set("0")
    if(var16.get()==1):
        txtCarlton_Hill_Cake .configure(state=NORMAL)
    elif var16.get()==0:
        txtQueen_Dark_Cake.configure(state=DISABLED)
        E_Queen_Dark_Cake.set("0")

#======================================================================
DateofOrder.set(time.strftime("%d/%m/%y"))


var1.set("0")
var2.set("0")
var3.set("0")
var4.set("0")
var5.set("0")
var6.set("0")
var7.set("0")
var8.set("0")
var9.set("0")
var10.set("0")
var11.set("0")
var12.set("0")
var13.set("0")
var14.set("0")
var15.set("0")
var16.set("0")

#======================Drinks======================#
Latta = Checkbutton(f1aa,text="Latta \t", variable=var1,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=0,sticky=W)
Espresso = Checkbutton(f1aa,text="Expresso \t", variable=var2,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=1,sticky=W)
Iced_Latta = Checkbutton(f1aa,text="Café Gelado \t", variable=var3,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=2,sticky=W)
Vale_Coffee = Checkbutton(f1aa,text="Café do Vale \t", variable=var4,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=3,sticky=W)
Cappuccino = Checkbutton(f1aa,text="Cappuccino \t", variable=var5,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=4,sticky=W)
African_Coffee = Checkbutton(f1aa,text="Café Africano \t", variable=var6,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=5,sticky=W)
American_Coffee = Checkbutton(f1aa,text="Café Americano \t", variable=var7,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=6,sticky=W)
Iced_Cappuccino = Checkbutton(f1aa,text="Cappuccinno Gelado \t", variable=var8,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=7,sticky=W)

#============================= Cakes =================#
Coffee_Cake = Checkbutton(f1ab,text="Bolo de Café \t", variable=var9,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=0,sticky=W)
Red_Velvet_Cake = Checkbutton(f1ab,text="Bolo Red Velvet \t", variable=var10,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=1,sticky=W)
Black_Forest_Cake = Checkbutton(f1ab,text="Bolo Nega Maluca \t", variable=var11,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=2,sticky=W)
Boston_Cream_Cake = Checkbutton(f1ab,text="Bolo de Limão \t", variable=var12,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=3,sticky=W)
Lagos_Chocolate_Cake = Checkbutton(f1ab,text="Bolo de Leite Ninho \t", variable=var13,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=4,sticky=W)
Kilburn_Chocolate_Cake = Checkbutton(f1ab,text="Bolo de Nutella \t", variable=var14,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=5,sticky=W)
Carlton_Hill_Cake = Checkbutton(f1ab,text="Bolo de Nozes \t", variable=var15,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold')).grid(row=6,sticky=W)
Queen_Dark_Cake = Checkbutton(f1ab,text="Donuts \t", variable=var16,onvalue=1, offvalue=0,
                    font=('amaranth',18,'bold'), command=chkbutton_value).grid(row=7,sticky=W)

#============================= Enter Widgets for Drinks =================#

txtLatta=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Latta,state=DISABLED)
txtLatta.grid(row=0,column=1)

txtEspresso=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Espresso,state=DISABLED)
txtEspresso.grid(row=1,column=1)

txtIced_Latta =Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Iced_Latta,state=DISABLED)
txtIced_Latta .grid(row=2,column=1)

txtVale_Coffee=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Vale_Coffee,state=DISABLED)
txtVale_Coffee.grid(row=3,column=1)

txtCappuccino=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Cappuccino,state=DISABLED)
txtCappuccino.grid(row=4,column=1)

txtAfrican_Coffee=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_African_Coffee,state=DISABLED)
txtAfrican_Coffee.grid(row=5,column=1)

txtAmerican_Coffee=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_American_Coffee,state=DISABLED)
txtAmerican_Coffee.grid(row=6,column=1)

txtIced_Cappuccino=Entry(f1aa,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Iced_Cappuccino,state=DISABLED)
txtIced_Cappuccino.grid(row=7,column=1)

#============================ Enter Widgets for Cakes =================#
txtCoffee_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Coffee_Cake,state=DISABLED)
txtCoffee_Cake.grid(row=0,column=1)

txtRed_Velvet_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Red_Velvet_Cake,state=DISABLED)
txtRed_Velvet_Cake.grid(row=1,column=1)

txtBlack_Forest_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Black_Forest_Cake,state=DISABLED)
txtBlack_Forest_Cake.grid(row=2,column=1)

txtBoston_Cream_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Boston_Cream_Cake,state=DISABLED)
txtBoston_Cream_Cake.grid(row=3,column=1)

txtLagos_Chocolate_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Lagos_Chocolate_Cake,state=DISABLED)
txtLagos_Chocolate_Cake.grid(row=4,column=1)

txtKilburn_Chocolate_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Kilburn_Chocolate_Cake,state=DISABLED)
txtKilburn_Chocolate_Cake.grid(row=5,column=1)

txtCarlton_Hill_Cake=Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Carlton_Hill_Cake,state=DISABLED)
txtCarlton_Hill_Cake.grid(row=6,column=1)

txtQueen_Dark_Cake =Entry(f1ab,font=('amaranth',16,'bold'),bd=8,width=6,justify='left',textvariable=E_Queen_Dark_Cake,state=DISABLED)
txtQueen_Dark_Cake .grid(row=7,column=1)

#===============================Information================================
lblReceipt=Label(ft2,font=('amaranth',12,'bold'), text='Pedidos',bd=2,anchor='w')
lblReceipt.grid(row=0,column=0,sticky=W)
txtReceipt=Text(ft2, width=59, height=22, bg="white", bd=8,font=('amaranth',11,'bold'))
txtReceipt.grid(row=1,column=0)



#===============================Cost Items Information================================
lblCostofDrinks=Label(f2aa,font=('amaranth',16,'bold'),text="Total das Bebidas", bd=8)
lblCostofDrinks.grid(row=2,column=0,sticky=W)
txtCostofDrinks=Entry(f2aa,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=CostofDrinks)
txtCostofDrinks.grid(row=2,column=1)

lblCostofCakes=Label(f2aa,font=('amaranth',16,'bold'),text="Total das Comidas", bd=8)
lblCostofCakes.grid(row=3,column=0,sticky=W)
txtCostofCakes=Entry(f2aa,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=CostofCakes)
txtCostofCakes.grid(row=3,column=1)

lblServiceCharge=Label(f2aa,font=('amaranth',16,'bold'),text="Taxa de Serviço", bd=8)
lblServiceCharge.grid(row=4,column=0,sticky=W)
txtServiceCharge=Entry(f2aa,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=ServiceCharge)
txtServiceCharge.grid(row=4,column=1)
#=============================== Payment Information================================


lblPaidTax=Label(f2ab,font=('amaranth',16,'bold'),text="Taxas", bd=8)
lblPaidTax.grid(row=2,column=0,sticky=W)
txtPaidTax=Entry(f2ab,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=PaidTax)
txtPaidTax.grid(row=2,column=1)

lblSubTotal=Label(f2ab,font=('amaranth',16,'bold'),text="SubTotal", bd=8)
lblSubTotal.grid(row=3,column=0,sticky=W)
txtSubTotal=Entry(f2ab,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=SubTotal)
txtSubTotal.grid(row=3,column=1)

lblTotalCost=Label(f2ab,font=('amaranth',16,'bold'),text="Total", bd=8)
lblTotalCost.grid(row=4,column=0,sticky=W)
txtTotalCost=Entry(f2ab,font=('amaranth',16,'bold'),bd=8,insertwidth=2,justify='left', textvariable=TotalCost)
txtTotalCost.grid(row=4,column=1)


#===============================Button================================
btnTotal=Button(fb2,padx=16,pady=1,bd=4,fg="light blue",font=('amaranth',16,'bold'),width=5,text="Total",command=CostOfItem).grid(row=0,column=0)

btnReceipt=Button(fb2,padx=16,pady=1,bd=4,fg="black",font=('amaranth',16,'bold'),width=5,text="Pedidos",command=Receipt).grid(row=0,column=1)

btnReset=Button(fb2,padx=16,pady=1,bd=4,fg="black",font=('amaranth',16,'bold'),width=5,text="Zerar",command=Reset).grid(row=0,column=2)

btnExit=Button(fb2,padx=16,pady=1,bd=4,fg="red",font=('amaranth',16,'bold'),width=5,text="Sair",command=qExit).grid(row=0,column=3)


root.mainloop()



