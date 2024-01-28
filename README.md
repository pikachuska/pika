# PIKA
A pika language

# КАК ИСПОЛЬЗОВАТЬ

### MAIN.PIKA
*pika/src/main.pika*
```
const { default: Lexer } = require("./Lexer");
const { default: Parser } = require("./Parser");

const code = `
    //Тут весь скрипт main.pika
    сумма = 2 ПЛЮС 2.
    ВЫВОД сумма.
`;

const lexer = new Lexer(code);

lexer.lexAnalysis();

const parser = new Parser(lexer.tokenList);

const rootNode = parser.parseCode();

parser.run(rootNode);

```
Изменяйте файл main.pika но только
```
const code = `

             `;
```
# КАК ОН РАБОТАЕТ

Весь язык написан на *TypeScript* и вы можете его дополнять если вы его знаете.

# ПРИМЕРЫ

```
один = 1.
два = 2.
ВЫВОД один ПЛЮС два.
```
Всегда на конце точка - во многих языках стоит **;** тут же **.** потому что этот язык поддерживает только русский и частично тут соблюдаются правила русского языка. Разберёи скрипт и посмотри как он работает.
```
один = 1.
```
Один это переменная а 1 это значение переменной, на конце точка.
```
переменная = число знак окончания
```
-----------------------------------------------------------------------
```
два = 2.
```
Тут тоже самое так что думаю можно не объяснять.
```
ВЫВОД один ПЛЮС два.
```
Слово вывод это значит вывести в консоль один это переменная ПЛЮС это плюс и два это тоже переменная, на конце также стоит точка.
```
ВЫВЕСТИ В КОНСОЛЬ переменная1 ПЛЮС переменная2 знак окончания
```
Вот что пока есть в языке
```
export const tokenTypesList = {
    'NUMBER': new TokenType('NUMBER', '[0-9]*'),
    'VARIABLE': new TokenType('VARIABLE', '[а-я]*'),
    'SEMICOLON': new TokenType('SEMICOLON', '\\.'),
    'SPACE': new TokenType('SPACE', '[ \\n\\t\\r]'),
    'ASSIGN': new TokenType('ASSIGN', '\\='),
    'LOG': new TokenType('LOG', 'ВЫВОД'),
    'PLUS': new TokenType('PLUS', 'ПЛЮС'),
    'MINUS': new TokenType('MINUS', 'МИНУС'),
    'LPAR': new TokenType('LPAR', '\\('),
    'RPAR': new TokenType('RPAR', '\\)'),
}
```
# Пример на *JavaScript* и *Pika*
Вот пример на *JavaScript* и на *Pika*:

*JavaScript*
```javascript
var one = 1;
var two = 2;
console.log(1 + 2);
```
*Pika*
```ru
один = 1.
два = 2.
ВЫВОД один ПЛЮС два.
```
