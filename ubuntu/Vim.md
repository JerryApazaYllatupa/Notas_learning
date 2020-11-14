# Git 

## ¿Como subir un respositorio a github?

```bash
git add . 
git commit -m "no tiene que aver ningun archivo en are de working"
git remote add origin https://github.com/JerryApazaYllatupa/LearningNotes.git
git remote -v
git pull --allow-unrelated-histories origin master 
git push --force origin master "Si hay problemas al hacer un push al repositorio"
git push origin master
```

