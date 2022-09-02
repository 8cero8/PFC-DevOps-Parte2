# PFC-DevOps-Parte2
Parte 2 prueba DevOps

EL CÓDIGO DE LA PARTE 2: 


import time
from selenium import webdriver
from selenium.webdriver.common.by import By


# se carga el driver de google chrome
driver = webdriver.Chrome("/Users/MrRobot/PythonProject/chromedriver")
#CI 50379263  port 8111
driver.get("http://localhost:8111")

#Hacemos web scrapping y buscamos el campo para ingresar el usuario por ID
elemento1 = driver.find_element(By.ID, "user")
elemento1.clear()
elemento1.send_keys("root")

#Hacemos web scrapping y buscamos el campo para ingresar la contraseña por NAME
elemento2 = driver.find_element(By.NAME, "pass")
elemento2.clear()
elemento2.send_keys("password")

elemento2.submit()
driver.get("http://localhost:8111")
driver.execute_script('document.querySelector("#CreateTicketInQueue > div.create-wide > input").click()')
elemento3 = driver.find_element(By.XPATH, '//*[@id="TitleBox--_Ticket_Create_html--messagedetails----Q3JlYXRlIGEgbmV3IHRpY2tldCBpbiBHZW5lcmFs---0"]/div/div/div[4]/div[2]/input')
elemento3.click()
elemento3.send_keys('testing')
elemento3.submit()
time.sleep(20)
driver.close()
