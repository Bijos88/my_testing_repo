# my_testing_repo

import webbrowser, sys, pyperclip

if len(sys.argv)> 1:
    address = "".join(sys.argv[1:])

else:
    address = pyperclip.paste()

webrowser.open("https://www.google.com/maps/place/imaddre")

