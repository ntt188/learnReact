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
## 3. Creat React App (folder 3)
- Tạo dự án với React + Webpack
- Tạo dự án với creat-react-app
- NPM, NPX và YARN là gì?
    - NPM
        - project scope
            - npm install react react-dom --save => dependencies
            - npm i react react-dom => dependencies 

            - npm install --save-dev react react-dom => devDependencies
            - npm i -D react react-dom => devDependencies

            Xóa dự án
            - npm uninstall react react-dom
        - global scope
            - npm i --global creat-react-app
            - npm i -g creat-react-app

            gỡ
            - npm uninstall -g creat-react-app
    - NPX
        - tại sao dùng NPX?
            đỡ phải cài những thư viện này lên máy
        - Gặp lỗi khi: npx create-react-app tiktok
    - YARN & NPM
    - YARN install
    - Lưu ý:
        - Luôn bật development server (npm start || yarn start)
- CRA Folder Struture
## 4. Hooks
- **Hooks là gì ?**
    gắn vào hay móc vào
    là những hàm được viết sẵn đc cũng cấp sẵn bởi reactjs
    1. chỉ dùng cho function component
    2. Component đơn giản và trở nên dễ hiểu
        - Không bị chia logic ra như method trong lifecycle của Class Component
        - Không cần sử dung "this"
    3. Sử dụng Hooks khi nào?
        - Dự án mới => Hooks
        - Dự án cũ 
            - Component mới => function component + Hooks
            - Component cũ => Giữ nguyên có time tối ưu sau
        - Logic nghiệp vụ cần sử dụng các tính chất của OOP => Class Component
    4. Người mới nên bát đầu từ Function hay Class Component?
        Func
    5. Có kết hợp sử dụng Function component & Class component được không?
        Được
- **useState hook**
    - Dùng khi nào?
        Khi muốn dữ liệu thay đổi thì giao diện tự động được 
        cập nhật (render lại theo dữ liệu).

    - Cách dùng
        ```jsx 
        import { userState } from 'react'

        function Component() {
            cons [state, setState] = useState(initState)

            ...
        }
        ```
    - Lưu ý
        - Component được re-render sau khi `setState`
        - Innitial state chỉ dùng cho lần đầu
        - Set state với callback?
        - Innitial state với callback?
        - Set state là thay thế state bằng giá trị mới 
    - Two-way binding trong React? **https://reactgo.com/two-way-data-binding-react/**
        - Lưu ý:
            1. Array
            2. Reference types
        - Ví dụ:
            1. Random gift
                ```jsx
                import { useState } from "react";

                const gifts = [
                'CPU i9',
                'RAM 32GB RGB',
                'RGB Keyboard'
                ]

                function App() {
                const [gift, setGift] = useState();

                const randomGift = () => {
                    const index = Math.floor(Math.random() * gifts.length)
                
                    setGift(gifts[index]);
                }

                return (
                    <div className="App" style={{padding:32}}>
                    <h1>{gift || 'Chưa có phần thưởng'}</h1>
                    <button onClick={randomGift}>Lây thưởng</button>      
                    </div>
                );
                }

                export default App;
                ```
            2. Two-way binding
                * Input:
                    ```jsx
                    import { useState } from "react";

                    function App() {
                    const [name, setName] = useState('');
                    const [email, setEmail] = useState('');

                    const handSubmit = () => {
                        //CALL API
                        console.log({
                        name,
                        email
                        })
                    }

                    return (
                        <div className="App" style={{padding:32}}>
                        <input 
                            value={name}
                            onChange={e => setName(e.target.value)}
                        />
                        <input 
                            value={email}
                            onChange={e => setEmail(e.target.value)}
                        />
                        <button onClick={handSubmit}>Register</button>
                        </div>
                    );
                    }

                    export default App;
                    ```
                * radio:
                    ```jsx
                    import { useState } from "react";

                    // Response from API
                    const courses = [
                    {
                        id: 1,
                        name: 'HTML, CSS'
                    },
                    {
                        id: 2,
                        name: 'Javascrip'
                    },
                    {
                        id: 3,
                        name: 'ReactJS'
                    }
                    ]

                    function App() {
                    const [checked, setChecked] = useState()
                    
                    const handSubmit = () => {
                        console.log({id: checked})
                    }

                    return (
                        <div className="App" style={{padding:32}}>
                        {courses.map(course => (
                            <div key={course.id}>
                            <input 
                                type="radio" 
                                checked={checked === course.id}
                                onChange={() => setChecked(course.id)}
                            />
                            {course.name}
                            </div>
                        ))}
                        <button onClick={handSubmit}>Register</button>
                        </div>
                    );
                    }

                    export default App;
                    ```
                * checkbox
                    ```jsx
                    import { useState } from "react";

                    // Response from API
                    const courses = [
                    {
                        id: 1,
                        name: 'HTML, CSS'
                    },
                    {
                        id: 2,
                        name: 'Javascrip'
                    },
                    {
                        id: 3,
                        name: 'ReactJS'
                    }
                    ]

                    function App() {
                    const [checked, setChecked] = useState([])
                    console.log(checked)
                    
                    const handleCheck = (id) => {
                        setChecked(prev => {
                        const isChecked = checked.includes(id)

                        if(isChecked) {
                            return checked.filter(item => item !== id)
                        } else {
                            return [...prev, id]
                        }
                        })
                    }

                    const handSubmit = () => {
                        //Call API
                        console.log({ids: checked})
                    }

                    return (
                        <div className="App" style={{padding:32}}>
                        {courses.map(course => (
                            <div key={course.id}>
                            <input 
                                type="checkbox" 
                                checked={checked.includes(course.id)}
                                onChange={() => handleCheck(course.id)}
                            />
                            {course.name}
                            </div>
                        ))}
                        <button onClick={handSubmit}>Register</button>
                        </div>
                    );
                    }

                    export default App;
                    ```
            3. Todolish: ***Làm dưới phần bài tập***
    - Bài tập:
        **Lưu ý:** nhớ import thư viện cần dùng "import { useState } from "react"
        1. Tăng thêm 1 đơn vị mỗi lần click vào button:
            ```jsx
            import { useState } from "react";

            function App() {
                const [counter, setCounter] = useState(1);

                const handleIncrease = () => {
                    setCounter(counter + 1)
                }
                
                return (
                    <div className="App" style={{padding:32}}>
                        <h1>{counter}</h1>
                        <button onClick={handleIncrease}>Increase</button>
                    </div>
                );
            }

            export default App;
            ```
        2. Todolish:
            ```jsx
            import { useState } from "react";
            
            function App() {
                const [jobs, setJobs] = useState(() => {
                    const storageJobs = JSON.parse(localStorage.getItem('jobs'));
                    return storageJobs || []
                });
                const [job, setJob] = useState('');

                const handleSubmit = () => {
                    setJobs(arr => {
                    const newJobs = [...arr, job];

                    //save to local storage
                    const jsonJobs = JSON.stringify(newJobs);
                    localStorage.setItem('jobs', jsonJobs);

                    return newJobs;
                    });
                    setJob('');
                }

                
                return (
                    <div className="App" style={{padding:32}}>
                        <input value={job} onChange={e => setJob(e.target.value)} />
                        <button onClick={handleSubmit}>Add</button>

                        <ul>
                            {jobs.map((job, key) => <li key={key}>{job}</li>)}
                        </ul>
                    </div>
                );
            }

            export default App;
            ```
- **Mounted & Unmounted**(Gắn vào và gỡ ra)
    - Là thuật ngữ khi ta tạo ra một thẻ và ẩn nó đi trên UI
        * Tạo một file **Content.js** tại thư mục **src**
            ```jsx
            function Content() {
                return (
                    <h1>Xin chào mọi người</h1>
                )
            }

            export default Content
            ```
        * Tại file **App.js**
            ```jsx
            import { useState } from "react";
            import Content from "./Content";

            function App() {
                const [show, setShow] = useState(false);

                return (
                    <div className="App" style={{padding:32}}>
                    <button onClick={() => setShow(!show)}>Togger</button>
                    {show && <Content />}
                    </div>
                );
                }

                export default App;
            ```
- **useEffect hook**