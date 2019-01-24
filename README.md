# ShippingCost
#This is a program that calculates the weight of a package and determines the cheapest method of shipping

#Calculates the weight of the package by the pound being shipped on Ground

def ground_shipping_cost(weight):
  
  if weight < 2:
    pound_price = 1.50
  if weight <= 6:
    pound_price = 3
  elif weight <= 10:
    pound_price = 4
  else:
    pound_price = 4.75
    
  return 20 + (pound_price *  weight)

#Prints the total cost to ground ship package according to it's weight   

print(ground_shipping_cost(8.4))

#Premium Ground Shipping Price

ship_premium = 125

#Calculates the weight of the package by the pound being shipped on Drone

def drone_shipping_cost(weight):
  if weight <= 2:
    pound_price = 4.50
  elif weight <= 6:
    pound_price = 9
  elif weight <= 10:
    pound_price = 12
  else:
    pound_price = 14.25
  
  return (pound_price * weight)
  
print(drone_shipping_cost(1.5))

#Finds the cheapest shipping method and then ells the user

def cheapest_shipping_print(weight):
  
  ground = ground_shipping_cost(weight)
  premium = ship_premium
  drone = drone_shipping_cost(weight)
  
  if ground < premium and ground < drone:
    method = "Standard shipping."
    cost = ground
  elif premium < ground and premium < drone:
    method = "Premium Shipping"
    cost = premium
  else:
    method = "Drone Shipping"
    cost = drone
    
  #$%.2f acts as a float to display the dollar amount and %s acts as a string  
  
  print("The cheapest shipping method that we have is $%.2f with %s shipping. " % (cost, method))

cheapest_shipping_print(3)
cheapest_shipping_print(17)
cheapest_shipping_print(23)
  
  
  


