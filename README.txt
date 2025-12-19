Ce dossier contient le TP Concurrency & Resilience.

1. Démarrer le stack Docker :
   docker compose up -d --build

2. Lancer les tests de charge :
   ./loadtest.sh BOOK_ID 50
   ou
   .\loadtest.ps1 -BookId BOOK_ID -Requests 50

3. Vérifier le stock final :
   curl http://localhost:8081/api/books

4. Tester le fallback :
   docker compose stop pricing-service
   ./loadtest.sh ID_FALLBACK 30

5. Vérifier les métriques :
   curl http://localhost:8081/actuator/metrics
