#!/bin/bash

clear

declare -A size_menu=(["small"]=7 ["medium"]=9 ["large"]=11 ["x-large"]=13)

size_array=( "small" "medium" "large" "x-large" )

declare -A cart_count_array=()

declare -A topping_menu=([sausage]=8 [pepperoni]=8 [cheese]=6 [pineapple]=7 [meat-lovers]=10)

toppings_array=( "cheese" "pineapple" "sausage" "pepperoni" "meat-lovers" )

declare -A cart_price_array=()

typeofpizza()
{
read -p "What type of pizza would you like to order today? >>   " type

for i in "${toppings_array[@]}"
   do 
        if [ "$type" == "$i" ]
        then
                pizza_selection="$i"
                cart_count_array+=("{$cart_count_array[0]}" "$pizza_selection")
		cart_price_array+=("{$cart_price_array[0]}" "{$topping_menu[$pizza_selection]}")
        fi
   done
}

sizeofpizza()
{
read -p "What size of $pizza_selection pizza would you like to order today? >>   " bigness

for s in "${size_array[@]}"
   do 
        if [ "$bigness" == "$s" ]
        then
                pizza_size_selection="$s"
                cart_count_array+=("{$cart_count_array[@]}" "$pizza_size_selection")
		echo "$pizza_size_selection $pizza_selection pizza has been added to your cart"

        fi
   done
}

addpizza()
{
read -p "Would you like to add another pizza to your oder? >>   " order
 
if [ "$order" == "yes" ]
        then
        echo " "
        sleep 1
        typeofpizza
        sizeofpizza
        addpizza
elif [ "$order" == "no" ]
         then
         echo " "
         echo "Your order is being processed..."
fi
}


carryout()
{
echo " "
read -p "What is the name for the order? >>	" name
echo " "
read -p "Can I get a contact number please? >>	" number
}

delivery()
{
echo " "
read -p "What is the name for the order? >>     " name
echo " "
read -p "Can I get a contact number please? >>  " number
echo " "
read -p "And what is the address we will be deliverying to? >>   " deliver
}



echo "---------- Welcome to Pizza Pizza ----------"
echo "----- Where you can be sure that Pizza -----"
echo "------------- Really is Pizza! -------------"
echo " "
sleep 2
echo " "

read -p "Is this order for carry out or delivery? >>    " cord
if [ $cord == "carryout" ]
then
carryout
elif [ $cord == "delivery" ]
then
delivery
fi

sleep 1
clear

echo "______________________________________________"
echo " "
echo "-------------- Pizza Pizza Menu --------------"
echo "______________________________________________"
echo " "
echo " Cheese Pizza  $ 6	Pineapple Pizza	$ 7 "
echo " "
echo " Sausage Pizza $ 8	Pepperoni Pizza $ 8 "
echo " "
echo " Meat Lovers   $ 10 "
echo "_____________________________________________ "
echo "	small	medium	large	x-large "
echo "_____________________________________________ "
echo " "
typeofpizza
echo " "
echo " "
sizeofpizza
echo " "
echo " "

addpizza

sleep 2
clear

echo "__________________________________"
echo " "
echo " ------------ Receipt -----------"
echo "__________________________________"
echo " "
echo "NAME:" $name 
echo "PHONE:" $number
echo "ADDRESS if out for delivery:"
echo $deliver
echo "YOUR ITEMS:"
echo ${cart_count_array[@]} "pizza"
echo " "
echo "The total comes to: $"${size_menu[$pizza_size_selection]}
echo " "
echo "Pleaes come back and see us again!"
echo "__________________________________"
