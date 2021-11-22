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

У нас есть форма:

<form:form modelAttribute="user" method="post" action="/url метода на который мы хотим передать данные">
    <form:input path="название того поля юзера что хотим передать например name" type="text">
</form:form>

И примем отправленные параметры с помощбю аннотации @RequestParam на контроллере (С помощью этой аннотации можем принимать если параметров не много):

@PostMapping("/test")
    public String test(@RequestParam("name") String name){
        User user = new User();
        user.setName(name);
        return "successPage";
    }
    
НО есть способ проще с помощью аннотации @ModelAttribute

Её можно ставить над методом - тогда этот примениться для всех существующих в контроллере методов у которых есть Model model, и в эту моель поместиться ещё model.addAttribute("message", "welcome to our website!");

@ModelAttribute("message")
    public String sendMessage(){
        return "welcome to our website!";
    }
