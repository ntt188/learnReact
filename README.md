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
### useState hook
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
### Mounted & Unmounted (Gắn vào và gỡ ra)
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
### useEffect hook
- Side Effect: là khi ta tác động xảy ra dẫn tới dữ liệu bị thay đổi.
- Kiến thức cần có:
    - Events: Add / remove event listener
    - Observer pattern: Subscribe / unsubscribe
    - Closure
    - Timers: setInterval, setTimeout, clearInterval, clearTimeout
    - useState
    - Mounted / Unmounted
    - ===
    - Call API
- Có 3 cách dùng useEffect:
    1.  userEffect(callback)
    2.  userEffect(callback, [])
    3.  userEffect(callback, [deps])
- Những thứ cần làm được
    1. Update DOM
        - F8 blog title (sử dụng **userEffect(callback)**)
        **Dùng lại file App.js của Mounted & Unmounted ở trên**
        * Tạo một file **Content.js** tại thư mục **src**
        ```jsx
        import { useEffect, useState } from "react"

        // 1*.  userEffect(callback)
        // - Gọi callback mỗi khi component re-render
        // - Gọi callback sau khi component thêm element vào DOM
        // 2.  userEffect(callback, [])
        // 3.  userEffect(callback, [deps])

        // ----------Lý thuyết chung------------------
        // 1. Callback luôn được gọi sau khi component mounted

        function Content() {

            const [title, setTitle] = useState('')

            useEffect(() => {
                document.title = title
            })

            return (
                <div>
                    <input 
                        value={title}
                        onChange={e => setTitle(e.target.value)}
                    />
                </div>
            )
        }

        export default Content
        ```
    2. Call API **truy cập (https://jsonplaceholder.typicode.com/) để lấy API về test**
        **Dùng lại file App.js của Mounted & Unmounted ở trên**
        * Tạo một file **Content.js** tại thư mục **src**
        * (sử dụng **userEffect(callback, [])**)
        ```jsx
        import { useEffect, useState } from "react"

        // 1.  userEffect(callback)
        // - Gọi callback mỗi khi component re-render
        // - Gọi callback sau khi component thêm element vào DOM
        // 2*.  userEffect(callback, [])
        // - Chỉ gọi callback 1 lần sau khi component mounted
        // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
        // 3.  userEffect(callback, [deps])

        // ----------Lý thuyết chung------------------
        // 1. Callback luôn được gọi sau khi component mounted

        function Content() {

            const [title, setTitle] = useState('')
            const [posts, setPosts] = useState([])

            useEffect(() => {
                fetch('https://jsonplaceholder.typicode.com/posts')
                    .then(res => res.json())
                    .then(posts => {
                        setPosts(posts)
                    })
            }, [])

            return (
                <div>
                    <input 
                        value={title}
                        onChange={e => setTitle(e.target.value)}
                    />
                    <ul>
                        {posts.map(post => (
                            <li key={post.id}>{post.title}</li>
                        ))}
                    </ul>
                </div>
            )
        }

        export default Content
        ```
        * Tạo một file **Content.js** tại thư mục **src**
        * (sử dụng **userEffect(callback, [deps])**)
        ```jsx
        import { useEffect, useState } from "react"

        // 1.  userEffect(callback)
        // - Gọi callback mỗi khi component re-render
        // - Gọi callback sau khi component thêm element vào DOM
        // 2.  userEffect(callback, [])
        // - Chỉ gọi callback 1 lần sau khi component mounted
        // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
        // 3.  userEffect(callback, [deps])
        // - Callback sẽ được gọi lại mỗi khi deps thay đổi

        // ----------Lý thuyết chung------------------
        // 1. Callback luôn được gọi sau khi component mounted

        const tabs = ['posts', 'comments', 'albums']

        function Content() {

            const [title, setTitle] = useState('')
            const [posts, setPosts] = useState([])
            const [type, setType] = useState('posts')

            useEffect(() => {
                fetch(`https://jsonplaceholder.typicode.com/${type}`)
                    .then(res => res.json())
                    .then(posts => {
                        setPosts(posts)
                    })
            }, [type])

            return (
                <div>
                    {tabs.map(tab => (
                        <button 
                            key={tab}
                            style={type === tab ? {
                                color: '#fff',
                                backgroundColor: '#333'
                            } : {}}
                            onClick={() => setType(tab)}
                        >
                            {tab}
                        </button>
                    ))}
                    <input 
                        value={title}
                        onChange={e => setTitle(e.target.value)}
                    />
                    <ul>
                        {posts.map(post => (
                            <li key={post.id}>{post.title || post.name}</li>
                        ))}
                    </ul>
                </div>
            )
        }

        export default Content
        ```
    3. Listen DOM event
        - Scroll
            **Dùng lại file App.js của Mounted & Unmounted ở trên**
            * Tạo một file **Content.js** tại thư mục **src**
            ```js
            import { useEffect, useState } from "react"

            // 1.  userEffect(callback)
            // - Gọi callback mỗi khi component re-render
            // - Gọi callback sau khi component thêm element vào DOM
            // 2.  userEffect(callback, [])
            // - Chỉ gọi callback 1 lần sau khi component mounted
            // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
            // 3.  userEffect(callback, [deps])
            // - Callback sẽ được gọi lại mỗi khi deps thay đổi

            // ----------Lý thuyết chung------------------
            // 1. Callback luôn được gọi sau khi component mounted
            // 2. Clearup function luôn được gọi trước khi component unmounted (tránh rò rỉ bộ nhớ)

            const tabs = ['posts', 'comments', 'albums']

            function Content() {

                const [posts, setPosts] = useState([])
                const [type, setType] = useState('posts')
                const [showGoToTop, setShowGoToTop] = useState(false)

                useEffect(() => {
                    fetch(`https://jsonplaceholder.typicode.com/${type}`)
                        .then(res => res.json())
                        .then(posts => {
                            setPosts(posts)
                        })
                }, [type])

                useEffect(() => {

                    const handleScroll = () => {
                        if(window.scrollY >= 200){
                            setShowGoToTop(true)
                        } else {
                            setShowGoToTop(false)
                        }
                    }

                    window.addEventListener('scroll', handleScroll)

                    // Clearup function (tránh rò rỉ bộ nhớ khi ta mounted một component mới)
                    return () => {
                        window.removeEventListener('scroll', handleScroll)
                    }
                }, [])

                return (
                    <div>
                        {tabs.map(tab => (
                            <button 
                                key={tab}
                                style={type === tab ? {
                                    color: '#fff',
                                    backgroundColor: '#333'
                                } : {}}
                                onClick={() => setType(tab)}
                            >
                                {tab}
                            </button>
                        ))}
                        <ul>
                            {posts.map(post => (
                                <li key={post.id}>{post.title || post.name}</li>
                            ))}
                        </ul>
                        {showGoToTop && (
                            <button
                                style={{
                                    position: 'fixed',
                                    right: 20,
                                    bottom: 20
                                }}
                            >
                                Go to Top
                            </button>
                        )}
                    </div>
                )
            }

            export default Content
            ```
        - Resize
            **Dùng lại file App.js của Mounted & Unmounted ở trên**
            * Tạo một file **Content.js** tại thư mục **src**
            ```jsx
            import { useEffect, useState } from "react"

            // 1.  userEffect(callback)
            // - Gọi callback mỗi khi component re-render
            // - Gọi callback sau khi component thêm element vào DOM
            // 2.  userEffect(callback, [])
            // - Chỉ gọi callback 1 lần sau khi component mounted
            // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
            // 3.  userEffect(callback, [deps])
            // - Callback sẽ được gọi lại mỗi khi deps thay đổi

            // ----------Lý thuyết chung------------------
            // 1. Callback luôn được gọi sau khi component mounted
            // 2. Clearup function luôn được gọi trước khi component unmounted (tránh rò rỉ bộ nhớ)

            function Content() {

                const [width, setWidth] = useState(window.innerWidth)

                useEffect(() => {
                    const handleResize = () => {
                        setWidth(window.innerWidth)
                    }

                    window.addEventListener('resize', handleResize)

                    return () => {
                        window.removeEventListener('resize', handleResize)
                    }
                }, [])

                return (
                    <div>
                        <h1>{width}</h1>
                    </div>
                )
            }

            export default Content
            ```
    4. Clearup
        - Remove listener / Unsubscribe
        - Clear timer
        **Dùng lại file App.js của Mounted & Unmounted ở trên**
        * Tạo một file **Content.js** tại thư mục **src**
        ```jsx
        import { useEffect, useState } from "react"

        // 1.  userEffect(callback)
        // - Gọi callback mỗi khi component re-render
        // - Gọi callback sau khi component thêm element vào DOM
        // 2.  userEffect(callback, [])
        // - Chỉ gọi callback 1 lần sau khi component mounted
        // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
        // 3.  userEffect(callback, [deps])
        // - Callback sẽ được gọi lại mỗi khi deps thay đổi

        // ----------Lý thuyết chung------------------
        // 1. Callback luôn được gọi sau khi component mounted
        // 2. Clearup function luôn được gọi trước khi component unmounted (tránh rò rỉ bộ nhớ)
        // 3. Clearup function luôn được gọi trước khi callback được gọi (trừ lần mounted)

        function Content() {

            const [countdown, setCountdown] = useState(100)

            // Sử dụng setInterval
            useEffect(() => {
                const timerId = setInterval(() => {
                    setCountdown(prev => prev - 1)
                }, 1000)

                return () => clearInterval(timerId)
            }, [])

            // sử dung
            // useEffect(() => {
            //     const timerId = setTimeout(() => {
            //         setCountdown(countdown - 1)
            //     }, 1000)

            //     return () => clearTimeout(timerId)
            // }, [countdown])

            return (
                <div>
                    <h1>{countdown}</h1>
                </div>
            )
        }

        export default Content
        ```   
        1. Preview avatar **Khắc phục tình trạng thay đổi những vẫn lưu trong bộ nhớ của dữ liệu cũ** (lever senior)
            ```jsx
            import { useEffect, useState } from "react"

            // 1.  userEffect(callback)
            // - Gọi callback mỗi khi component re-render
            // - Gọi callback sau khi component thêm element vào DOM
            // 2.  userEffect(callback, [])
            // - Chỉ gọi callback 1 lần sau khi component mounted
            // - Sử dụng khi bạn muốn thực hiện 1 logic gì 1 lần khi component được mounted ko muốn nó gọi lại khi re-render
            // 3.  userEffect(callback, [deps])
            // - Callback sẽ được gọi lại mỗi khi deps thay đổi

            // ----------Lý thuyết chung------------------
            // 1. Callback luôn được gọi sau khi component mounted
            // 2. Clearup function luôn được gọi trước khi component unmounted (tránh rò rỉ bộ nhớ)
            // 3. Clearup function luôn được gọi trước khi callback được gọi (trừ lần mounted)

            function Content() {

                const [avata, setAvata] = useState()

                useEffect(() => {


                    //Cleanup
                    return () => {
                        avata && URL.revokeObjectURL(avata.preview)
                    }
                }, [avata])

                const handlePreviewAvatar = (e) => {
                    const file = e.target.files[0]

                    file.preview = URL.createObjectURL(file)

                    setAvata(file)
                }

                return (
                    <div>
                        <input 
                            type="file"
                            onChange={handlePreviewAvatar}
                        />
                        {avata && (
                            <img src={avata.preview} alt="" width="80%"/>
                        )}
                    </div>
                )
            }

            export default Content
            ```
        2. useEffect with fake Chat App
        **Dùng lại file App.js của Mounted & Unmounted ở trên**
        * Tạo một file **Content.js** tại thư mục **src**
        ```jsx
        import { useEffect, useState } from "react"

        const lessons = [
            {
                id: 1,
                name: 'ReactJS là gì? Tại sao nên học ReactJS?'
            },
            {
                id: 2,
                name: 'SPA/MPA là gì?'
            },
            {
                id: 3,
                name: 'Arrow function'
            }
        ]

        function Content() {

            const [lessonId, setLessonId] = useState(1)

            useEffect(() => {

                const handleComment = ({detail}) => {
                    console.log(detail);
                }

                window.addEventListener(`lesson-${lessonId}`, handleComment)

                return () => {
                    window.removeEventListener(`lesson-${lessonId}`, handleComment)
                }
            }, [lessonId])

            return (
                <div>
                    <ul>
                        {lessons.map(lesson => (
                            <li
                                key={lesson.id}
                                style={{
                                    color: lessonId ===lesson.id ?
                                        'red' :
                                        '#333'
                                }}
                                onClick={() => setLessonId(lesson.id)}
                            >
                                {lesson.name}
                            </li>
                        ))}
                    </ul>
                </div>
            )
        }

        export default Content
        ```
        * Tại file **index.js** tạo một function event emitComment để fake comment
        ```jsx
        import React from 'react';
        import ReactDOM from 'react-dom/client';
        import './index.css';
        import App from './App';
        import reportWebVitals from './reportWebVitals';

        // Fake comments
        function emitComment(id) {

        setInterval(() => {
            window.dispatchEvent(
            new CustomEvent(`lesson-${id}`, {
                detail: `Nội dung Comment của lesson ${id}`
            })
            )
        }, 2000)

        }

        emitComment(1)
        emitComment(2)
        emitComment(3)

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(
        <React.StrictMode>
            <App />
        </React.StrictMode>
        );

        // If you want to start measuring performance in your app, pass a function
        // to log results (for example: reportWebVitals(console.log))
        // or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
        reportWebVitals();
        ```
* Thứ tự công việc được làm:
    1. Cập nhật lại state
    2. Cập nhật lại DOM (mutated)
    3. Render lại UI
    4. Gọi cleanup nếu deps thay đổi
    5. Gọi useEffect callback
### useLayoutEffect hook
* Thứ tự công việc được làm:
    1. Cập nhật lại state
    2. Cập nhật lại DOM (mutated)
    3. Gọi cleanup nếu deps thay đổi (sync)
    4. Gọi useLayoutEffect callback (sync)
    5. Render lại UI
- Cũng tương tự useEffect những thứ tự công việc của useLayoutEffect khác là nó render ở cuối. Và useLayoutEffect áp dụng khi bạn muốn set lại 2 lần trong một lần chạy.
    ```jsx
    import { useLayoutEffect, useState } from "react"

    function Content() {

        const [count, setCount] = useState(0)

        useLayoutEffect(() => {
            if(count > 3) {
                setCount(0)
            }
        }, [count])

        const handleRun = () => {
            setCount(count + 1)
        }

        return (
            <div>
                <h1>{count}</h1>
                <button onClick={handleRun}>Run</button>
            </div>
        )
    }

    export default Content
    ```
### useRef hook
* **Chỉ sử dụng giá trị khởi tạo trong lần đầu tiên render**
* **Hàm này luôn trả về giá trị là một object** có key là **current**
    ```js
    import { useEffect, useRef, useState } from "react";

    // Lưu các giá trị qua một tham chiếu bên ngoài
    // function component

    function App() {
        const [count, setCount] = useState(60)

        const timerId = useRef()
        const prevCount = useRef()
        const h1Ref = useRef()

        // Lưu giá trị trước đó khi thay đổi
        useEffect(() => {
            prevCount.current = count
        }, [count])

        // lấy ra vị trí của element
        useEffect(() => {
            const rect = h1Ref.current.getBoundingClientRect()

            console.log(rect)
        })

        const handleStart = () => {
            timerId.current = setInterval(() => {
            setCount(prevCount => prevCount - 1)
            }, 1000)
        }

        const handleStop = () => {
            clearInterval(timerId.current)
        }

        console.log(count, prevCount.current)

        return (
            <div style={{padding: 20}}>
                <h1 ref={h1Ref}>{count}</h1>
                <button onClick={handleStart}>Start</button>
                <button onClick={handleStop}>Stop</button>
            </div>
        )
    }

    export default App;
    ```
### Phương thức React.memo HOC(Higher order component)
- React.memo được gọi là Higher order component (HOC). Dùng để ghi nhớ các props của một component, quyết định xem có render lại component đó hay không để tối ưu về hiệu năng.

- Ngắn gọn React.memo dùng để xử lý component tránh re-render trong tình huống không cần thiết.
* Tại file **App.js**
```jsx
import { useState } from "react";
import Content from "./Content";

// Lưu các giá trị qua một tham chiếu bên ngoài
// function component

function App() {
    const [count, setCount] = useState(0)

  const increase = () => {
    setCount(count + 1)
  }

  return (
      <div style={{padding: '10px 32px'}}>
          <Content />
          <h1>{count}</h1>
          <button onClick={increase}>Click me!</button>
      </div>
  )
}

export default App;
```
* Tạo file **Content.js** tại thư mục **src**
```jsx
import { memo } from "react"

function Content() {
    return (
        <h2>HELLO ANH EM F8</h2>
    )
}

export default memo(Content)
```
### useCallback hook
- Dùng để sử lý khi bạn dùm **React.memo()** giúp ko tạo ra các function component ko cần thiết
* Tại file **App.js**
```jsx
import { useCallback, useState } from "react";
import Content from "./Content";

// Lưu các giá trị qua một tham chiếu bên ngoài
// function component

function App() {
    const [count, setCount] = useState(0)

  const handleIncrease = useCallback(() => {
    setCount(count + 1)
  })

  return (
      <div style={{padding: '10px 32px'}}>
          <Content onIncrease={handleIncrease} />
          <h1>{count}</h1>
      </div>
  )
}

export default App;
```
* Tạo file **Content.js** tại thư mục **src**
```jsx
import { memo } from "react"

function Content({onIncrease}) {
    return (
        <>
            <h2>HELLO ANH EM F8</h2>
            <button onClick={onIncrease}>Click me!</button>
        </>
    )
}

export default memo(Content)
```
### useMemo hook
- Giúp tránh thực hiện lại một logic nào đó ko cần thiết
```jsx
import { useMemo, useRef, useState } from "react";

function App() {
    const [name, setName] = useState('')
  const [price, setPrice] = useState('')
  const [products, setProducts] = useState([])
  
  const nameRef = useRef()

  const handleSubmit = () => {
    setProducts([...products, {
      name,
      // Chuyển chữu thành số thêm dấu '+' đằng trước
      price: +price
    }])
    setName('')
    setPrice('')
    nameRef.current.focus()
  }

  const total = useMemo(() => {
    const result = products.reduce((result, prod) => 
    result + prod.price, 0)
    return result
  }, [products])

  return (
      <div style={{padding: '10px 32px'}}>
          <input 
            value={name}
            placeholder="Enter name..."
            ref={nameRef}
            onChange={e => setName(e.target.value)}
          />
          <br />
          <input 
            value={price}
            placeholder="Enter price..."
            onChange={e => setPrice(e.target.value)}
          />
          <br />
          <button onClick={handleSubmit}>Add</button>
          <br />
          Total: {total}
          <ul>
            {products.map((product, index) => (
              <li key={index}>{product.name} - {product.price}</li>
            ))}
          </ul>
      </div>
  )
}

export default App;
```
### useReducer hook
- Với useState:
    1. Init state: 0
    2. Action: Up (state + 1) / Down (state - 1)
- Với useReducer:
    1. Init state: 0
    2. Action: Up (state + 1) / Down (state - 1)
    3. Reducer
    4. Dispatch
    ```jsx
    import { useReducer } from "react";

    // Init state
    const initState = 0

    // Actions
    const UP_ACTION = 'up'
    const DOWN_ACTION = 'down'

    // Reducer
    const reducer = (state, action) => {
    switch(action) {
        case UP_ACTION:
        return state + 1
        case DOWN_ACTION:
        return state - 1
        default:
        throw new Error('Invalid action')
    }
    }

    function App() {
        const [count, dispatch] = useReducer(reducer, initState)

        return (
            <div style={{padding: '0 20px'}}>
                <h1>{count}</h1>
                <button 
                    onClick={() => dispatch(DOWN_ACTION)}
                >
                    Down
                </button>
                <button
                    onClick={() => dispatch(UP_ACTION)}
                >
                    Up
                </button>
            </div>
        )
    }

    export default App;
    ```
* **Todo App**
```jsx
import { useReducer, useRef } from "react";

// useReducer
  // 1. Init state
  const initState = {
    job: '',
    jobs: []
  }

  // 2. Actions
  const SET_JOB = 'set_job'
  const ADD_JOB = 'add_job'
  const DELETE_JOB = 'delete_job'

  const setJob = payload => {
    return {
      type: SET_JOB,
      payload
    }
  }

  const addJob = payload => {
    return {
      type: ADD_JOB,
      payload
    }
  }

  const deleteJob = payload => {
    return {
      type: DELETE_JOB,
      payload
    }
  }

  // 3. Reducer
  const reduce = (state, action) => {
    
    switch(action.type) {
      case SET_JOB:
        return {
          ...state,
          job: action.payload
        }
      case ADD_JOB:
        return {
          ...state,
          jobs: [...state.jobs, action.payload]
        }
      case DELETE_JOB:
        const newJobs = [...state.jobs]

        newJobs.splice(action.payload, 1)

        return {
          ...state,
          jobs: newJobs
        }
      default:
        throw new Error('Invalid action')
    }
  }

  // 4. Dispatch 

function App() {
    const [state, dispatch] = useReducer(reduce, initState)

  const { job, jobs } = state

  const inputRef = useRef();

  const handleSubmit = () => {
    dispatch(addJob(job))
    dispatch(setJob(''))

    inputRef.current.focus()
  }

  return (
      <div style={{padding: '0 20px'}}>
        <h3>Todo</h3>
        <input 
          value={job}
          placeholder="Enter todo..."
          onChange={e => {
            dispatch(setJob(e.target.value))
          }}
          ref={inputRef}
        />
        <button
          onClick={handleSubmit}
        >
          Add
        </button>
        <ul>
          {jobs.map((job, index) => (
            <li key={index}>
              {job}
              <span onClick={() => dispatch(deleteJob(index))}>&times;</span>
            </li>
          ))}
        </ul>
      </div>
  )
}

export default App;
```
### useContext hook
* đơn giản hóa việc truyền dữ liệu từ component cha xuống component con mà ko qua gián tiếp
* Tại file **App.css** tại thư mục **src**
```css
.dark {
  color: #fff;
  background-color: #333;
}
```
* Tạo file **Content.js** tại thư mục **src**
```jsx
import Paragraph from "./Paragraph"

function Content() {
    return (
        <div>
            <Paragraph />
        </div>
    )
}

export default Content
```
* Tạo file **Paragraph.js.css** tại thư mục **src**
```jsx
import { useContext } from "react"
import { ThemeContext } from "./App"

function Paragraph() {
    const theme = useContext(ThemeContext)
    return (
        <p className={theme}>
            Context provides a way to pass data through the component tree without having to pass props down manually at every lever.
        </p>
    )
}

export default Paragraph
```
* Tại file **App.js** tại thư mục **src**
```jsx
import { useState, createContext } from "react";
import Content from "./Content"
import './App.css'

export const ThemeContext = createContext()


// Context
// CompA => CompB => CompC

// 1. Create context
// 2. Provider
// 3. Consumer

function App() {
  
    const [theme, setTheme] = useState('dark')
  
    const toggleTheme = () => {
      setTheme(theme === 'dark' ? 'light' : 'dark')
    }

    return (
        <ThemeContext.Provider value={theme}>
          <div style={{padding: 20}}>
              <button onClick={toggleTheme}>Toggle theme</button>
              <Content />
          </div>
        </ThemeContext.Provider>      
    )
}

export default App;
```
### Context + useReducer
* Tại file **index.js** trong thư mục **src** ta bọc ngoài thẻ APP môt thẻ <StoreProvider>
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import { StoreProvider } from './store';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <StoreProvider>
      <App />
    </StoreProvider>
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```
* Tại file **App.js**
```jsx
import { useStore, actions } from "./store";

function App() {
    const [state, dispatch] = useStore()
    const { todos, todoInput } = state

    const handleAdd = () => {
        dispatch(actions.addTodo(todoInput))
    }

    return (
        <div>
            <input 
                value={todoInput}
                placeholder="Enter todo..."
                onChange={e => {
                  dispatch(actions.setTodoInput(e.target.value))
                }}
            />
            <button onClick={handleAdd}>Add</button>
            {todos.map((todo, index) => 
                <li key={index}>{todo}</li>
            )}
        </div>
    )
}

export default App;
```
#### Tạo thư mục có tên là store trong thư mục src
* Tạo file **action.js** và **reduce.js** và **constants.js** để sử dụng hook useReducer
    - **action.js**
        ```jsx
        import { ADD_TODO, SET_TODO_INPUT } from "./constants";

        export const setTodoInput = payload => ({
            type: SET_TODO_INPUT,
            payload
        })

        export const addTodo = payload => ({
            type: ADD_TODO,
            payload
        })
        ```
    - **constants.js**
        ```jsx
        export const SET_TODO_INPUT = 'set_todo_input'
        export const ADD_TODO = 'add_todo'
        ```
    - **reduce.js**
        ```jsx
        import { SET_TODO_INPUT, ADD_TODO } from "./constants"

        const initState = {
            todos: [],
            todoInput: ''
        }

        function reducer (state, action) {
            switch (action.type) {
                case SET_TODO_INPUT:
                    return {
                        ...state,
                        todoInput: action.payload
                    }
                case ADD_TODO:
                    return {
                        ...state,
                        todos: [...state.todos, action.payload]
                    }
                default:
                    throw new Error('Invalid action.')
            }
        }


        export { initState }
        export default reducer
        ```
* Tạo Component **Provider.js**
```jsx
import { useReducer } from "react"
import Context from "./Context"
import reducer, {initState} from "./reducer"
import logger from "./logger"

function Provider({ children }) {
    const [state, dispatch] = useReducer(logger(reducer), initState)

    return (
        <Context.Provider value={[state, dispatch]}>
            {children}
        </Context.Provider>
    )
}

export default Provider
```
* Tạo Component **Context.js**
```jsx
import { createContext } from "react";

const Context = createContext()

export default Context
```
* Tạo file **hook.js**
```jsx
import { useContext } from 'react'
import Context from "./Context"

export const useStore = () => {
    const [state, dispatch] = useContext(Context)

    return [state, dispatch]
}
```
* Tạo file **index.js**
```jsx
export { default as StoreProvider} from './Provider'
export { default as StoreContext } from './Context'
export * from './hooks'

export * as actions from './actions'
```
* Tạo file **logger.js** để log ra các dữ liệu mà ta thao tác
```jsx
import { actions } from ".";

function logger(reducer) {
    return (prevState, action) => {
        console.group(action.type)
        console.log('Prev state: ', prevState)
        console.log('Action: ', action)
        
        const nextState = reducer(prevState, action)

        console.log('Next state: ', nextState)
        console.groupEnd()
        return nextState
    }
}

export default logger
```
### useImperativeHandle hook
* Tùy chỉnh được ref của 1 function component
## CSS, SCSS và CSS modules
### Sử dụng CSS