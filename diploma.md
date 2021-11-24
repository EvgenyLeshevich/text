GET-запрос

Когда будет сортировка по параметрам или поиск какихто товаров, ты я должен делать это get-запросом и в адресной строке передавать ключ-значение.

Что бы извлечь параметры из гет-запроса нужна аннотация @RequestParam: то есть когда мы передаёт url например http://localhost:8080/mobile?name=Apple&screen=Amoled, то в контроллере в Get-запросе что бы получить эти параметры мы должны написать @RequestParam("name") String name, @RequestParam("screen") String screen где в скабках находится ключ переданного параметра а в стринге его значение. Так же что бы не нужно было обязательно передавать параметры на этот адрес то нужно дописать в параметры required=false: @RequestParam("name", required=false) String name.

Что бы передавать данные со страницы на контроллер в паре ключ-значение нам нужно на html написать ссылку <a href="/mobile?name=Apple">Apple</a>. Это использовать можно при фильтрации по параметрам!!!!!!!!!!!!!!!!!!

Что бы извлечь информацию из адресной строки мы можем использовать:

@PathVariable("id") int id - id - нужная нам информация полученная из адресной строки поместиться в int id

-----------------------------------

POST-запрос

Для отправки данных с форм на сервер!

Данные передаются не в url, а в адресной строке

Пример отправки формы на контроллер нужно для начала передать в методе гет объект для которого форма создана:

@GetMapping("/test")
    public String test(Model model) {
        model.addAttribute("user", new User());
        return "test";
    }
    
![image](https://user-images.githubusercontent.com/73518823/142919207-c09db505-0e47-4dbd-b7c6-a301d5fa88ee.png)

У нас есть форма:

<form:form modelAttribute="user" method="post" action="/url метода на который мы хотим передать данные">
    <form:input path="название того поля юзера что хотим передать например name" type="text">
</form:form>

![image](https://user-images.githubusercontent.com/73518823/142918683-3ec21129-fbc5-471a-99cc-4859c00f463f.png)

И примем отправленные параметры с помощбю аннотации @RequestParam на контроллере (С помощью этой аннотации можем принимать если параметров не много):

@PostMapping("/test")
    public String test(@RequestParam("name") String name){
        User user = new User();
        user.setName(name);
        return "successPage";
    }
    
![image](https://user-images.githubusercontent.com/73518823/142919101-e01bf9c6-4e4d-4dce-ac64-6f99f95a940e.png)
    
НО есть другой способ с помощью аннотации @ModelAttribute

![image](https://user-images.githubusercontent.com/73518823/142919572-5da0b70e-d0a8-456e-884b-eaf56d6c1688.png)

Её можно ставить над методом - тогда этот примениться для всех существующих в контроллере методов у которых есть Model model, и в эту моель поместиться ещё model.addAttribute("message", "welcome to our website!");

@ModelAttribute("message")
    public String sendMessage(){
        return "welcome to our website!";
    }
    
![image](https://user-images.githubusercontent.com/73518823/142919656-9423d735-10e8-4755-ae86-103d5b68ce81.png)
 
 Когда мы вешаем аннтацию @ModelAttribute в аргументы метода на объект то это означает что мы из формы получаем поля этого объекта, спринг сам создаёт этот объект и присваивает ему значения которые мы передали
 
 ИТОГ будет @ModelAttribute("user") User user = model.addAttribute("user", new User());
 
 ![image](https://user-images.githubusercontent.com/73518823/142920489-b7067e6e-f3fa-4ee5-9385-84ef2a772f26.png)
 
 Если мы не передадим какое-то из полей то он примет значение 0 или null в зависимости от типа переменной поля

![image](https://user-images.githubusercontent.com/73518823/142977810-dffde284-f7a9-4800-8c44-699e030bb411.png)



