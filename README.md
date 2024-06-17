## Dependencies

To install the dependencies you can use the following commands:

- GLib (for project build)
```
sudo apt install libglib2.0-dev
```

- Doxygen (for documentation)
```
sudo apt install doxygen
```

- Ncurses (for interactive mode)
```
sudo apt install libncurses5-dev libncursesw5-dev
```

## How to run
#### Note: To run the program we suggest using the example dataset provided and add it inside *trabalho_pratico/dataset* or the larger example dataset at *trabalho_pratico/dataset_large*.
[dataset](https://github.com/Mackgame4/large_file_server/raw/main/dataset.zip)

[dataset_large](https://elearning.uminho.pt/bbcswebdav/pid-1396837-dt-content-rid-7277488_1/xid-7277488_1)

- To test your program in batch mode directly, you can use the following command:
```
./programa-principal dataset/data/ dataset/input.txt Resultados/
```
or simply:
```
./programa-principal dataset/data dataset/input.txt
```
- If you want to skip the file validation you can use the clean dataset folder:
```
./programa-principal dataset/data_clean dataset/input.txt
```
- If you dont want to use a file as input and use a command instead, or if you want to use the interactive mode, you can use the following command:
```
./programa-principal
```

#### Note: The execution of ./programa-testes is not necessary, it is only used to test the program by an automated test script.

## Documentation

- To generate the documentation you can use the following command:
```
make docs
```

- To clean the documentation files you can use the following command:
```
make clean-docs
```

- To open the documentation you can use the following command:
```
make open-docs
```

#### If you want to open the documentation manually, you can find it in the docs folder or use the following command:
```
xdg-open docs/html/index.html
```

## How to compile

- To compile the program you can use the following command:
```
make
```

- To clean the compiled files you can use the following command:
```
make clean
```

## Performance Check
```
sudo apt install valgrind
```

- To check the memory leaks you can use the following command:
```
valgrind --leak-check=full --show-leak-kinds=all --track-origins=yes ./programa-principal dataset/data dataset/input.txt
```

- Since were using GLib we can also use the following command to check for memory leaks:
```
G_DEBUG=gc-friendly G_SLICE=always-malloc valgrind --leak-check=full --show-leak-kinds=all  --suppressions=/usr/share/glib-2.0/valgrind/glib.supp --track-origins=yes ./programa-principal dataset/data dataset/input.txt
```

- To check the hole program output you can use the following command:
```
valgrind --leak-check=full --show-leak-kinds=all --track-origins=yes ./programa-testes dataset/data dataset/input.txt > log.txt
```

or:
```
./programa-principal dataset/data_clean dataset/input.txt > log.txt
```


- Using *programa-testes* instead of *programa-principal*, CPU time and memory usage will be shown (and also execute [unit tests](#unit-tests))

## Unit Tests
- Unit tests are executed as part of the automated test script, but can also be executed manually using the following command:
```
./programa-testes dataset/data_clean dataset/input.txt dataset/outputs
```

or:
```
./programa-testes dataset/data_clean dataset/input.txt dataset/outputs > log.txt
```

## Development Team
[a104365,Fábio Rafael Oliveira Magalhães,Mackgame4](https://github.com/Mackgame4)

[a100815,Miguel Tomás Antunes Pinto,Primenta](https://github.com/Primenta)

[a100557,Pedro Miguel Costa Azevedo,Pexometro](https://github.com/Pexometro)

**`Note:`** Do not ignore *.vscode/* and *.idea/* folders if existent, they are used to simplify the development process by making collaboration easier and fixing IDE source files search errors and <ins>**are not part of the project**</ins>.
