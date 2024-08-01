calls = 0
def count_calls():
    global calls
    calls+=1
    return calls
def string_info(string):
    count_calls()
    tuple = (len(string),string.upper(),string.lower())
    return tuple # Иначе в строке print(string_info('Capybara')) (и подобных) мы увидим None, так как если мы не возвращаем значения функции,то и принту печатать то нечего ведь мы вызвали функцию в принте,значит он должен напечатать её значение(которого БЕЗ return НЕ БУДЕТ!)

def is_contains(string , is_contains):
    count_calls()
    for i in range(len(is_contains)):
        if string.lower() == is_contains[i].lower():
            return True
    return False

print(string_info('Capybara'))
print(string_info('Armageddon'))
print(is_contains('Urban', ['ban', 'BaNaN', 'urBAN'])) # Urban ~ urBAN
print(is_contains('cycle', ['recycling', 'cyclic'])) # No matches
print(calls)
