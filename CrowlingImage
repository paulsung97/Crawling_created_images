from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import urllib.request
import time

# 크롬 브라우저 열기
driver = webdriver.Chrome()
driver.get("https://www.craiyon.com/")

# 페이지 스크롤 내리기
last_height = driver.execute_script("return document.body.scrollHeight")
scroll_height = int(last_height * 0.08)
driver.execute_script(f"window.scrollBy(0, {scroll_height});")

# 검색창에 검색어 입력하고 검색 버튼 클릭하기
wait = WebDriverWait(driver, 10)
for i in range(99):
    elem = wait.until(EC.presence_of_element_located((By.NAME, "prompt")))
    elem.send_keys(Keys.BACKSPACE*len("A real apple from various angles.")) // 해당 위치에 생성하고 싶은 내용을 적으세요 
    elem.send_keys("A real apple from various angles.") // 해당 위치에 생성하고 싶은 내용을 적으세요 위와 같은 내용을 적어주세요!
    elem.send_keys(Keys.RETURN)
    time.sleep(60)

    # 이미지 다운로드
    img_elements = driver.find_elements(By.CSS_SELECTOR, ".h-full.w-full.cursor-pointer.rounded-lg.border.border-medium-blue.object-cover.object-center")
    for i in range(9):
        try:
            img_elements[i].click()
            time.sleep(1)
            button_elements = driver.find_elements(By.CSS_SELECTOR, "#actions_buttons button")
            button_elements[1].click()
            time.sleep(1)
            button_elements[2].click()
            time.sleep(1)
            img_elements = driver.find_elements(By.CSS_SELECTOR, ".h-full.w-full.cursor-pointer.rounded-lg.border.border-medium-blue.object-cover.object-center")
        except:
            print("Cannot find download or close button, skipping download for this image.")
            img_elements = driver.find_elements(By.CSS_SELECTOR, ".h-full.w-full.cursor-pointer.rounded-lg.border.border-medium-blue.object-cover.object-center")
