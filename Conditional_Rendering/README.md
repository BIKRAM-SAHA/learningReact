[Back to Content](../README.md)

# Conditional Rendering
- We can use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.
- there are different ways to do this:
    - Using simple `if-else condition` while returning:
        - Let two components be
            ```javascript
            function UserGreeting(props) {
            return <h1>Welcome back!</h1>;
            }

            function GuestGreeting(props) {
            return <h1>Please sign up.</h1>;
            }
            ```
        - now the greeting component that displays either of these two depending if the user is logged in.
            ```javascript
            function Greeting(props) {
            const isLoggedIn = props.isLoggedIn;
            if (isLoggedIn) {
                return <UserGreeting />;
            }
            return <GuestGreeting />;
            }

            ReactDOM.render(
            // Try changing to isLoggedIn={true}:
            <Greeting isLoggedIn={false} />,
            document.getElementById('root')
            );
            ```
    - Using `Element variables` to store elements
        - We can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change.
        - Let two components be:
            ```javascript
            function LoginButton(props) {
            return (
                <button onClick={props.onClick}>
                Login
                </button>
            );
            }

            function LogoutButton(props) {
            return (
                <button onClick={props.onClick}>
                Logout
                </button>
            );
            }
            ```
        - We will create a stateful component called LoginControl which will render either <LoginButton /> or <LogoutButton /> depending on its current state.
            ```javascript
            class LoginControl extends React.Component {
            constructor(props) {
                super(props);
                this.handleLoginClick = this.handleLoginClick.bind(this);
                this.handleLogoutClick = this.handleLogoutClick.bind(this);
                this.state = {isLoggedIn: false};
            }
            handleLoginClick() {
                this.setState({isLoggedIn: true});
            }
            handleLogoutClick() {
                this.setState({isLoggedIn: false});
            }
            render() {
                const isLoggedIn = this.state.isLoggedIn;
                let button;

                if (isLoggedIn) {
                    button = <LogoutButton onClick={this.handleLogoutClick} />;
                } else {
                    button = <LoginButton onClick={this.handleLoginClick} />;
                }

                return (
                <div>
                    {button}
                </div>
                );
            }
            }

            ReactDOM.render(
            <LoginControl />,
            document.getElementById('root')
            );
            ```
    - Using Logical `&& Operator`
        - It works because in JavaScript, true && expression always evaluates to expression, and false && expression always evaluates to false.
        - Note that returning a falsy expression will still cause the element after && to be skipped but will return the falsy expression.
        - eg:
            ```javascript
            function Mailbox(props) {
            const unreadMessages = props.unreadMessages;
            return (
                <div>
                <h1>Hello!</h1>
                {unreadMessages.length > 0 &&
                    <h2>
                    You have {unreadMessages.length} unread messages.
                    </h2>
                }
                </div>
            );
            }

            const messages = ['React', 'Re: React', 'Re:Re: React'];
            ReactDOM.render(
            <Mailbox unreadMessages={messages} />,
            document.getElementById('root')
            );
            ```
    - Using `ternary operator`
        - eg:
        ```javascript
        render() {
        const isLoggedIn = this.state.isLoggedIn;
        return (
            <div>
            The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
            </div>
        );
        }
        ```



[Previous](../Handling_Events/README.md)
<br>

[Next](../Basic_Hooks/README.md)