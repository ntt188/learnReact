# learnReact
Lean React

## 1. React, ReactDOM (folder 1)
### - document.createElement() 
1. document.createElement()
    const h1 = document.createElement('h1');
2. document.body.appendChild(): thêm một phần tử con vào phần tử cha
    document.body.appendChild(h1);
3. consle.dir(): dùng để xem dạng g obj của element được lấy ra
4. innerText, id, className, style
    Thêm text vào thẻ
        h1.innerText = 'Hello!!'
    Thêm id vào thẻ
        h1.id = 'heading'
    Thêm class vào thẻ
        h1.className = 'test class-2'
    Thêm style inline vào thẻ
        h1.style.color = 'red'
        Hoặc thêm nhiều style
        Object.assign(h1.style, {
            color: 'blue',
            backgroundColor: '#333'
        })
### - React.createElement()
1. React.createElement() -> React element
2. So sánh với document.createElement() -> DOM element
3. Thay đổi: id, className, style,...
4. Thêm: text, html
5. Tạo:
    <h1 title="Hello" class="heading">Hello guys!</h1>
6. Tạo:
    <ul>
        <li>Javascript</li>
        <li>ReactJS</li>
    </ul>
7. Tạo:
    <div class="post-item">
        <h2 title="Học React tại F8">Học ReactJS</h2>
        <p>Học ReactJS từ cơ bản đến nâng cao</p>				
    </div>
### - ReactDOM
1. Tại sao phải dùng React-DOM?
    Để render được ReactElement
    Vậy nó là 1 thư viện là cầu nối giữa React và DOM
2. Tại sao lại tách React-DOM ra?
3. Render UI    

React-Native -> ios, Adroid

## 2. JSX, Components, Props (folder 2)
### - JSX -> Javascript XML
1. Luôn dùng React.createElement()? Vấn đề?
2. JSX? live demo: https://bit.ly/2VOIMN7
3. JSX không phải HTML,
    Cần có Javascript, Babel để dùng JSX
4. JSX và ReactDOM?
<ul>
    <li>Javascript</li>
    <li>ReactJS</li>
</ul>

//Thắng này sinh ra để bọc ngoài các thẻ element nếu bạn muốn thêm nhiều thẻ riêng biệt mà ko muốn bọc ngoài một thẻ cha
<React.Fragment></React.Fragment>
### - React element types (comment.html)
                    type	props									chidlren,...
                     |		|										|
React.createElement('h1', {className: 'heading', title: 'Hello'}, 'Hello guys!')

*Hooks

1. React element types: string, function/class
    - wrapper
        - Header -> Header component
        - Content -> Content comment
        - Footer -> Footer comment
2. Biểu diển đơn giản với JSX
### - Props là gì? Dùng props khi nào? (prop.html)
- React Element
    - Sử dụng props giống như với Attribute của thẻ HTML
    - 2 props class, for => className, htmlFor
    - Phải tuân theo quy ước có sẵn
- React comments
    - Sử dụng props giống như đối số của function
    - Tự do đặt tên props
        - Đặt theo camelCase
        - *Có thể bao gồm dấu gạch ngang
- Chú ý:
    - Prop "key" là prop đặc biệt
    - Props cơ bản là đối số của Component
        => Props có thể là bất cứ kiểu dữ liệu gì
    - Sử dụng destructuring

### PHẦN I
- DOM events?
    khác với DOM events của js(onclick) thì với react ta viết hoa chử cái đầu từ từ thứ 2 và không viết tắt
- Quy ước đặt tên Components (component2.html)
    Components do chúng ta tự định nghĩa phải viết in hoa ký tự đầu tiên
- Booleans, Null & Undefined không được render
- Kết hợp toán tử logic để render theo điều kiện

### PHẦN II
- Props trong JSX
    - Quy ước khi tạo Component khi truyền prop có 2 cách
        ta có thể dùng chuỗi bằng cách truyền qua dấu nháy kép
        hoặc truyền bằng expression thông qua cặp đấu {} nhưng expression ko nhận ifelse, for,... 
        chỉ nhận các giá trị hoặc toán tử 3 ngôi
        <YourComponent
            propName1="String literals"
            propName2={expression}
        />
    - Props default to "true"
    - Spead/Rest props
        Khi muốn tạo ra một component gon gàng đẹp đẽ
        function Input({label, ...inputProps}) {
            return (
                <div>
                    <label>{label}</label>
                    <input {...inputProps} />
                </div>
            )
        }

        function App() {            
            return (
                <div id="wrapper">
                    <Input 
                        label="Full name"
                        type="checkbox"
                        placeholder="Enter name..."
                        title="Đây là input"
                    /> 
                </div>
            )
        }
    - Chidlren prop
        - <YourComponent>String literals</YourComponent>
        - <YourComponent>{expression}</YourComponent>
    - Render props (render-props.html)