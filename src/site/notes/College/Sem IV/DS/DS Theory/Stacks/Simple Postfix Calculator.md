---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-theory/stacks/simple-postfix-calculator/"}
---

```C++

#include <iostream>

#include <stack>

#include <string>

#include <cmath>

  

double calculate(std::string postfix) {

    std::stack<double> st;

    for (int i = 0; i < postfix.length(); i++) {

        if (postfix[i] >= '0' && postfix[i] <= '9') {

            st.push((double)(postfix[i] - '0'));

        } else {

            double num1 = st.top(); st.pop();

            double num2 = st.top(); st.pop();

            switch (postfix[i]) {

                case '+':

                    st.push(num2 + num1);

                    break;

                case '-':

                    st.push(num2 - num1);

                    break;

                case '*':

                    st.push(num2 * num1);

                    break;

                case '/':

                    st.push(num2 / num1);

                    break;

                case '^':

                    st.push(pow(num2,num1));

                    break;

            }

        }

    }

    return st.top();

}

  

int main() {

    std::string postfix = "23*5+";

    std::cout << "The value of the postfix expression '" << postfix << "' is: " << calculate(postfix) << std::endl;

    return 0;

}

```

