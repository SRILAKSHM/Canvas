# Canvas
Assignment
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import unittest
from time import sleep
from selenium.webdriver.common.action_chains import ActionChains

driver = webdriver.Chrome('C:\\Users\svinnakota\\Downloads\\chromedriver_win32 (1)\\chromedriver.exe')

driver.get('http://www.htmlcanvasstudio.com/')

driver.implicitly_wait(10)


driver.find_element_by_xpath('//*[@id="editor"]/div[1]/input[2]').click()

canvas = driver.find_element_by_id("container")

drawing = ActionChains(driver)

drawing.click_and_hold(canvas)

# Horizontal line

drawing.move_by_offset(100, 0).move_by_offset(150, 0).click(None).release().perform()

# Vertical line

drawing.click_and_hold(canvas)

drawing.move_by_offset(55, -55).move_by_offset(-55, -55).click(None).release().perform()

drawing.click_and_hold(canvas)

drawing.move_by_offset(-55, 55).move_by_offset(55, 55).click(None).release().perform()


driver.find_element_by_xpath('//*[@id="editor"]/div[1]/input[3]').click()

b = driver.find_element_by_id('imageView')

drawing.click_and_hold(canvas)

drawing.move_by_offset(50, -50).move_by_offset(50, 100).click(None).release().perform()


driver.find_element_by_xpath('//*[@id="editor"]/div[1]/input[5]').click()

drawing.click_and_hold(canvas).move_by_offset(55, -55).move_by_offset(-55, -55).click(None).release().perform()

