---
title: "Uge 38 - Interfaces, arv og HTTP-statuskoder"
date: 2026-09-14
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?
På ForeDoomWatch gjorde jeg DAO'en mere robust. DAO'en kræver nu, at T extender interfacet IEntity, så alle typer har en getID. Det gør, at Update kan hente den eksisterende entitet og kaste en ApiException med HTTP-status 404, Not Found, hvis ID'et ikke findes. Jeg kaster denne exception for at sikre, at merge ikke opretter et nyt objekt af typen T i databasen, hvor den i stedet skulle opdatere et eksisterende.

```java
try {
    T existing = entityManager.find(entityClass, t.getID());
    if (existing == null) {
        throw new ApiException(HttpStatus.NOT_FOUND.value(),
                entityClass.getSimpleName() + " ID could not be found");
    }
    merged = entityManager.merge(t);
    entityManager.getTransaction().commit();
} catch (PersistenceException e) {
    if (entityManager.getTransaction().isActive()) {
        entityManager.getTransaction().rollback();
    }
    throw new ApiException(HttpStatus.INTERNAL_SERVER_ERROR.value(),
            "Update " + entityClass.getSimpleName()
                    + " failed with error message: " + e.getMessage());
}
```

Jeg erstattede også tallene 400, 404 og 500 med HttpStatus-enummet, så koden er mere læsbar.

## Hvad var svært?

Det var svært at finde ud af, hvordan jeg skulle tjekke, om en entity havde et ID. Jeg blev nødt til at spørge min lærer Thomas, som kom med IEntity-idéen, en let og elegant løsning. Interfacet garanterer nemlig over for den generiske DAO, at de entities, der bruger den, har et ID. Det er essentielt for at kunne fange exceptions i update, da merge bygger på ID'et.

## Hvad lærte jeg?

Jeg lærte, hvor kraftfulde og smarte interfaces og arv er. Jeg er typisk dårlig til at bruge dem, fordi projekterne i skolen sjældent er store nok til, at de bliver relevante. Men efter at have lavet den generiske DAO og IEntity kan jeg se, hvordan man kan spare meget kode, og at det også ser pænere ud og er let at læse.