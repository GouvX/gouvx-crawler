# GouvX crawler

Ce repo contient les araignées utilisées sur le site GouvX. C'est la première étape de la chaine de traitement.

Les araignées se "promènent" sur les pages du gouvernement et vont extraire les informations pour alimenter la base de données de gouvx.
Chaque araignée est configurée pour un site en particulier. Une liste non exhaustive des sites en *.gouv.fr peut être trouvée [ici](https://www.data.gouv.fr/fr/datasets/listes-des-sites-gouv-fr/).

## Pour lancer le crawler:
```bash
# exemple avec legifrance:

# scraper un url donné:
scrapy shell -s USER_AGENT="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/118.0.0.0 Safari/537.36" https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006074069/LEGISCTA000006157551/?anchor=LEGIARTI000006796412#LEGIARTI000006796412

# lancer l'aragnée sur le site:
rm -rf legifrance.csv legifrance.log
scrapy runspider legifrance_scraper.py -o legifrance.csv --logfile legifrance.log

```

## TODO:
- [x] créer un crawler pour service-public.fr
- [x] créer un crawler pour legifrance.gouv.fr
- [ ] créer un crawler pour code.travail.gouv.fr
- [ ] créer un crawler pour vie-publique.fr
- [ ] lancer les crawlers régulièrement pour vérifier les mises à jour