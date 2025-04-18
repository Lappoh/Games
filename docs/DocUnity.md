# Документация по разработке игр на Unity
## 1.Начало работы
### 1.1 Установка Unity
1. Скачайте Unity Hub с официального сайта.
2. Установите нужную версию Unity (рекомендуется LTS-версия, например, 2022.3).
3. Добавьте модули (Android, iOS, WebGL, если нужно).
   
### 1.2 Создание проекта
1. 2D (для платформеров, пиксельных игр)
2. 3D (для 3D-игр, шутеров)
3. URP/HDRP (для улучшенной графики)
4. Пустой проект (если нужна кастомизация)

## 2. Основы Unity
### 2.1 Интерфейс
1. Scene View – редактирование уровней.
2. Game View – тестирование игры.
3. Hierarchy – список объектов на сцене.
4. Inspector – настройка компонентов.
5. Project – файлы проекта.
6. Console – отладка ошибок.

### 2.2 Игровые объекты (GameObjects) и компоненты
1. GameObject – базовый объект (персонаж, платформа, свет).
2. Компоненты – добавляют функциональность (например, Rigidbody, Collider, Script).

Пример: создание персонажа
1. GameObject → 3D Object → Capsule (игрок).
2. Добавьте компоненты:
   Rigidbody (физика).
   Box Collider (столкновения).
   Character Controller (управление).

## 3. Скриптинг на С#
### 3.1 Основы
Скрипты должны наследоваться от MonoBehaviour.

Основные методы для разработки передвижения:

```
using UnityEngine;                                                                                                                        
public class PlayerMovement : MonoBehaviour                               
   {                                                                         
public float speed = 5f;                                               
void Update() {                                                        
float moveX = Input.GetAxis("Horizontal") * speed * Time.deltaTime; 
float moveZ = Input.GetAxis("Vertical") * speed * Time.deltaTime;  
transform.Translate(moveX, 0, moveZ);                              
}                                                                      
}        
```

### 3.2 Популярные API Unity
Представлены методы/классы которые чаще всего используются при разработке игр и их описания:
          
Input.GetKey() - Проверка нажатия клавиш.   
Instantiate() - Создание объектов в runtime. 
Destroy() - Удаление объекта.       
OnCollisionEnter() - Обработка столкновений.    
Time.deltaTime - Плавное движение.       


## 4.Физика и коллизии
### 4.1 Типы коллайдеров
  1. Box Collider – прямоугольник.
  2. Sphere Collider – сфера.
  3. Mesh Collider – точная форма модели (ресурсоемко).

### 4.2 Rigidbody
Объект с Rigidbody подвержен гравитации и физике.

Пример:
```
  public class Jump : MonoBehaviour                                    
  {                                                                    
    public float jumpForce = 5f;                                       
    private Rigidbody rb;                                              
    void Start() {                                                     
        rb = GetComponent<Rigidbody>();                                
    }                                                                  
    void Update() {                                                    
        if (Input.GetKeyDown(KeyCode.Space)) {                         
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);    
        }                                                              
    }                                                                  
  }                                                                    
```

## 5. UI и меню
### 5.1 Canvas
Представляет из себя белое полотно на которое можно наложить любые объекты, вызвать в любой момент или как-то взаимодействовать, для добавления полотна необходимо нажать следующее:
  GameObject → UI → Button/Text/Slider
  
### 5.2 Код для UI:
```
  using UnityEngine.UI;                          
  public class HealthBar : MonoBehaviour         
  {                                              
    public Slider slider;                        
    public void SetHealth(float health) {        
        slider.value = health;                   
    }                                            
  }                                              
```
## 6. Оптимизация
### 6.1 Gроизводительность
Используйте Object Pooling вместо Instantiate/Destroy.
Оптимизируйте Draw Calls (объединяйте меши).
Отключайте ненужные Update() с помощью enabled = false.

### 6.2 Профилирование
  Window → Analysis → Profiler – анализ нагрузки.
  Frame Debugger – просмотр рендеринга.
  
## 7. Публикация игры
### 7.1 Настройка билда
File → Build Settings → выберите платформу (PC, Android, WebGL).

Для мобильных игр:

  Настройте Player Settings (разрешение, ориентацию).
  
  Установите Keystore (для Android).
  
### 7.2 Публикация
  Steam/Itch.io – для ПК.
  
  Google Play/App Store – для мобильных.
  
  WebGL – для браузерных игр.
