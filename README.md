# react-note
state = { name: '' };
setName(name) {
  this.setState({ name });
}
      
const [name, setName] = useState('');
      
state = { count: 0 };
nextCount() {
  this.setState(prevState => ({
    ...prevState,
    count: prevState.count + 1,
  }));
}
      
const [count, setCount] = useState(0);
const nextCount = () =>
  setCount(prevValue => prevValue + 1);
      
componentDidMount() {
  API.getSomeThing();
}
      
useEffect(() => {
  API.getSomeThing();
}, []); // Phải thêm [] để không bị gọi API liên tục mỗi lần re-render
      
onBodyClick() {}
componentDidMount() {
  document
    .body
    .addEventListener('click', this.onBodyClick);
}
componentWillUnmount() {
  document
    .body
    .removeEventListener('click', this.onBodyClick);
}
      
const onBodyClick = () => {};
useEffect(() => {
  document
    .body
    .addEventListener('click', onBodyClick);
  return () => {
    document
      .body.
      removeEventListener('click', onBodyClick);
}, []);// Phải thêm [] để không bị gọi API liên tục mỗi lần re-render
      
doSomething() {}
componentDidMount() {
  doSomething();
}
componentDidUpdate() {
  doSomething();
}
      
const doSomething = () => {};
useEffect(() => {
  doSomething();
});
      
state = { count: 0 };
componentDidMount() {
  document.title = `clicked Count${this.state.count} times`;
}
componentDidUpdate(prevProps, prevState) {
  if (prevState.count !== this.state.count) {
    document.title = `clicked Count${this.state.count} times`;
  }
}
      
const [count, setCount] = useState(0);
useEffect(() => {
  document.title = `clicked Count${this.state.count} times`;
}, [count]); // Phải thêm [count] chỉ thực hiện set title nếu count trước và sau re-render thay đổi
      
componentDidMount() {
  API.setOnline();
}
componentWillUnmount() {
  API.setOffline();
}
        
useEffect(() => {
  API.setOnline();
  return () => API.setOffline();
}, []); // [] để ko bị gọi API liên tục khi re-render
        
state = { girlId: '001' }
componentDidMount() {
  API.sayILoveThisGirl(this.state.girlId);
}
componentDidUpdate(prevProps, prevState) {
  if (prevState.girlId !== this.state.girlId) {
    API.sayILoveThisGirl(this.state.girlId);
  }
}
componentWillUnmount() {
  API.sayGoodByMyLove(this.state.girlId);
}
        
const [girlId, setGirlId] = useState('001');
useEffect(() => {
  API.sayILoveThisGirl(girlId);
  return API.sayGoodByMyLove(girlId);
}, [girlId]);// [girlId] để ko bị gọi API liên tục nếu girlId trước và sau re-render không thay đổi
        
