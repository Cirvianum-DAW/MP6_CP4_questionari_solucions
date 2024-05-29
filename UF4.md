## QÜESTIONS UF4

#### 1. Quina funció utilitzaries per manejar una promesa que ha estat complerta?

- A) `promise.catch()`
- B) `promise.finally()`
- C) `promise.then()`
- D) `promise.handle()`

**Resposta correcta: C) `promise.then()`**

#### 2. Què es mostra a la consola quan s'executa el següent codi?

```javascript
async function processData(data) {
  if (!data) {
    throw new Error("No data provided");
  }
  return data * 2;
}

async function main() {
  try {
    let result = await processData(null);
    console.log(result);
  } catch (error) {
    console.error("Caught error:", error.message);
  }
}

main();
```

- A) Es mostra a la consola: `Caught error: No data provided`.
- B) Es mostra a la consola: `No data provided`.
- C) Es mostra a la consola: `undefined`.
- D) Es mostra a la consola: `Caught error: undefined`.

**Resposta correcta: A) Es mostra a la consola: `Caught error: No data provided`.**

#### 3. Què passa quan `sendData()` s'executa?

```javascript
async function sendData() {
  try {
    let response = await fetch("https://api.example.com/data", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        name: "John Doe",
        email: "john.doe@example.com",
      }),
    });
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}
sendData();
```

- A) S'envien les dades especificades i es mostra a la consola l'objecte de la resposta.
- B) S'envien les dades especificades però no es mostra res a la consola.
- C) No passa res perquè l'endpoint no accepta peticions `POST`.
- D) Es mostra a la consola un error perquè la petició `POST` no és vàlida.

**Resposta correcta: A) S'envien les dades especificades i es mostra a la consola l'objecte de la resposta.**

#### 4. Quina és la forma correcta de crear una nova promesa en JavaScript?

- A) `let promise = new Promise();`
- B) `let promise = new Promise(function(resolve, reject) {});`
- C) `let promise = Promise.resolve();`
- D) `let promise = new Promise(function() {});`

**Resposta correcta: B) `let promise = new Promise(function(resolve, reject) {});`**

#### 5. Com pots obtenir dades d'un usuari específic amb una petició GET utilitzant `fetch`?

```javascript
async function fetchUserData(userId) {
  try {
    // Què falta aquí?
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}
fetchUserData(1);
```

Quin codi seria necessari (aplicant lògica) per obtenir dades d'un usuari específic amb una petició GET utilitzant `fetch`?

- A) `let response = await fetch('https://api.example.com/users/' + "userId");`
- B) `let response = await fetch('https://api.example.com/users/${userId});`
- C) `let response = await fetch('https://api.example.com/users', { userId: userId });`
- D) `let response = await fetch('https://api.example.com/users', { method: 'GET', userId: userId });`

**Resposta correcta: B) `let response = await fetch('https://api.example.com/users/' + userId);`**

#### 6. Quina és la sortida esperada del següent codi?

```javascript
async function myFunction() {
  let result = await Promise.resolve("Hello");
  console.log(result);
}
myFunction();
```

- A) Hello
- B) undefined
- C) Promise {<fulfilled>: "Hello"}
- D) Error

**Resposta correcta: A) Hello**

#### 7. Com pots definir una funció asíncrona en JavaScript?

- A) `function async myFunction() {}`
- B) `async function myFunction() {}`
- C) `function myFunction() async {}`
- D) `function myFunction() { async }`

**Resposta correcta: B) `async function myFunction() {}`**

#### 8. Com pots capturar un error en una promesa?

- A) `promise.catch()`
- B) `promise.finally()`
- C) `promise.then()`
- D) `promise.error()`

**Resposta correcta: A) `promise.catch()`**

#### 9. Quina és la sortida esperada del següent codi que utilitza `fetch`?

```javascript
fetch("https://api.example.com/data")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

- A) Un objecte JavaScript que representa les dades de la resposta.
- B) Un objecte JSON.
- C) Un objecte XMLHttpRequest.
- D) Undefined.

**Resposta correcta: A) Un objecte JavaScript que representa les dades de la resposta.**

#### 10. Què es mostra a la consola quan s'executa el següent codi?

```javascript
Promise.resolve(1)
  .then((value) => {
    console.log(value); // ?    return value * 2;
  })
  .then((value) => {
    console.log(value); // ?
    return value * 3;
  })
  .then((value) => {
    console.log(value); // ?
    return value * 4;
  })
  .then((value) => {
    console.log(value); // ?
  });
```

- A) 1, 2, 6, 24
- B) 1, 2, 4, 8
- C) 1, 2, 6, 18
- D) 1, 2, 6, 24

**Resposta correcta: D) 1, 2, 6, 24**

#### 11. Quin és el resultat esperat del següent codi quan hi ha un error en la petició `fetch`?

```javascript
async function fetchData() {
  try {
    let response = await fetch("https://api.invalid-url.com/data");
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}
fetchData();
```

- A) Es mostra a la consola: `Fetch error: Error: Network response was not ok`.
- B) Es mostra a la consola: `Fetch error: Error: NetworkError when attempting to fetch resource`.
- C) Es mostra a la consola: `{ data: ... }` (les dades de la resposta).
- D) Es mostra a la consola: `Fetch error: TypeError: Failed to fetch`.

**Resposta correcta: D) Es mostra a la consola: `Fetch error: TypeError: Failed to fetch`.**

#### 12. Què passa quan una de les promeses en `Promise.all` falla?

```javascript
let promise1 = Promise.resolve(1);
let promise2 = Promise.reject("Error en la promesa");
let promise3 = Promise.resolve(3);

Promise.all([promise1, promise2, promise3])
  .then((values) => {
    console.log(values);
  })
  .catch((error) => {
    console.error("Error:", error);
  });
```

- A) Es mostra a la consola: `[1, 'Error en la promesa', 3]`.
- B) Es mostra a la consola: `Error: Error en la promesa`.
- C) Es mostra a la consola: `[1, undefined, 3]`.
- D) Es mostra a la consola: `Error: Error en la promesa` i les altres promeses no es processen.

**Resposta correcta: D) Es mostra a la consola: `Error: Error en la promesa` i les altres promeses no es processen.**

#### 13. Quina és la manera correcta de gestionar múltiples promeses que depenen una de l'altra?

- A) Utilitzant `Promise.all()`.
- B) Utilitzant `Promise.race()`.
- C) Utilitzant una combinació de `.then()` i `async/await`.
- D) No es poden gestionar múltiples promeses de manera dependent.

**Resposta correcta: C) Utilitzant una combinació de `.then()` i `async/await`.**

#### 14. Quin és la sortida esperada del següent codi?

```javascript
async function getData() {
  let promise1 = new Promise((resolve) =>
    setTimeout(() => resolve("Promesa 1"), 3000)
  );
  let promise2 = new Promise((resolve) =>
    setTimeout(() => resolve("Promesa 2"), 2000)
  );

  let results = await Promise.all([promise1, promise2]);
  console.log(results);
}

getData();
```

- A) ['Promesa 1', 'Promesa 2']
- B) ['Promesa 2', 'Promesa 1']
- C) undefined
- D) Promise {<pending>}

**Resposta correcta: B) ['Promesa 2', 'Promesa 1']**

#### 15. Què fa el mètode `response.json()` en el context d'una petició `fetch`?

- A) Converteix la resposta HTTP en un objecte JSON.
- B) Envia una resposta en format JavaScript al servidor.
- C) Envia una resposta en format JSON al servidor.
- D) Converteix la resposta HTTP en un objecte JavaScript.

**Resposta correcta: A) Converteix la resposta HTTP en un objecte JSON.**

#### 16. Quina és la sortida esperada del següent codi?

```javascript
async function getData() {
  try {
    let response = await fetch("https://api.example.com/data");
    let data = await response;
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
getData();
```

- A) Les dades de la resposta en format objecte JavaScript.
- B) Un objecte JSON.
- C) Un error.
- D) Undefined.

**Resposta correcta: C) Un error, ja que `response` no és un objecte JSON.**

#### 17. Quina és la diferència principal entre `await` i `.then()`?

- A) `await` només es pot utilitzar dins de funcions sincròniques, mentre que `.then()` es pot utilitzar en qualsevol lloc.
- B) `await` només es pot utilitzar dins de funcions asíncrones, mentre que `.then()` es pot utilitzar en qualsevol lloc.
- C) `await` és més ràpid que `.then()`.
- D) `await` és més lent que `.then()`.

**Resposta correcta: B) `await` només es pot utilitzar dins de funcions asíncrones, mentre que `.then()` es pot utilitzar en qualsevol lloc.**

#### 18. Quina és la sortida esperada del següent codi que fa una petició GET per obtenir dades?

```javascript
async function fetchData() {
  try {
    let response = await fetch("https://api.example.com/data");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}
fetchData();
```

- A) Un objecte JavaScript amb les dades de la resposta.
- B) Un objecte JSON amb les dades de la resposta.
- C) Un error perquè l'endpoint no és correcte.
- D) Undefined.

**Resposta correcta: A) Un objecte JavaScript amb les dades de la resposta.**

#### 19. Quina és la sortida esperada del següent codi?

```javascript
let promise = Promise.resolve(42);
promise.then((value) => {
  console.log(value);
});
```

- A) 42
- B) undefined
- C) Promise {<fulfilled>: 42}
- D) Error

**Resposta correcta: A) 42**

#### 20. Com pots enviar dades en una petició `POST` amb `fetch`?

- A) `fetch('https://api.example.com/data', { method: 'POST', body: JSON.stringify(data) })`
- B) `fetch('https://api.example.com/data', { method: 'POST', data: data })`
- C) `fetch.post('https://api.example.com/data', data)`
- D) `fetch.post('https://api.example.com/data', JSON.stringify(data))`

**Resposta correcta: A) `fetch('https://api.example.com/data', { method: 'POST', body: JSON.stringify(data) })`**
