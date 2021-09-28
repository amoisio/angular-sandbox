# Tour of heroes short takeaways

- The top-level moduel (ie. AppModule) is the application shell under which the app is rendered.
    - All components and depending modules must be defined here

- ng generate component <name>
- ng generate service <name>
- About Bindings
    - Angular binds to public members in templates
    - data properties with [name] - read them with @Input
    - handlers with (name)
    - model binding with [(name)] -> most probably binds the data like with [] and then binds to input event with () by default.

- Directives
    - *ngIf
    - *ngFor
- Async pipe
    - *ngFor="let hero in heroes$ | async"

- Observables instead of Promises
    - In generating code : of(..) => generates and Observable<T>
    - In calling code : call .subscribe on the observable
        - Call atleast once, otherwise observable code will not execute

- Routing
    - routing typically defined in its own module
    - routerLink directive on A-tag
    - route parameters: this.route.snapshot.paramMap.get("id")
    - route parameter definitions { path: 'detail/:id', component: HeroDetailComponent }

- RxJs (see the Search component)
    - Subject 

- HttpClient.get instead of fetch
    return this.http.get<Hero[]>(this.heroesUrl)
      .pipe(
        tap(_ => this.log('fetched heroes')),
        catchError(this.handleError<Hero[]>('getHeroes', []))
      );