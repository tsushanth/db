---
id: caseWhen
title: caseWhen
---

# Function: caseWhen()

## Call Signature

```ts
function caseWhen<C1, V1>(condition1, value1): CaseWhenResult<[V1], false>;
```

Defined in: [packages/db/src/query/builder/functions.ts:418](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L418)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

### Returns

`CaseWhenResult`\<\[`V1`\], `false`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, D>(
   condition1, 
   value1, 
defaultValue): CaseWhenResult<[V1, D], true>;
```

Defined in: [packages/db/src/query/builder/functions.ts:422](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L422)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### D

`D` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### defaultValue

`D`

### Returns

`CaseWhenResult`\<\[`V1`, `D`\], `true`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2>(
   condition1, 
   value1, 
   condition2, 
value2): CaseWhenResult<[V1, V2], false>;
```

Defined in: [packages/db/src/query/builder/functions.ts:427](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L427)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`\], `false`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, D>(
   condition1, 
   value1, 
   condition2, 
   value2, 
defaultValue): CaseWhenResult<[V1, V2, D], true>;
```

Defined in: [packages/db/src/query/builder/functions.ts:438](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L438)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### D

`D` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### defaultValue

`D`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `D`\], `true`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
value3): CaseWhenResult<[V1, V2, V3], false>;
```

Defined in: [packages/db/src/query/builder/functions.ts:451](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L451)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`\], `false`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, D>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
defaultValue): CaseWhenResult<[V1, V2, V3, D], true>;
```

Defined in: [packages/db/src/query/builder/functions.ts:466](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L466)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### D

`D` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### defaultValue

`D`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`, `D`\], `true`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, C4, V4>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
   condition4, 
value4): CaseWhenResult<[V1, V2, V3, V4], false>;
```

Defined in: [packages/db/src/query/builder/functions.ts:483](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L483)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### C4

`C4` *extends* `ExpressionLike`

#### V4

`V4` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### condition4

`C4`

#### value4

`V4`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`, `V4`\], `false`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, C4, V4, D>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
   condition4, 
   value4, 
defaultValue): CaseWhenResult<[V1, V2, V3, V4, D], true>;
```

Defined in: [packages/db/src/query/builder/functions.ts:502](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L502)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### C4

`C4` *extends* `ExpressionLike`

#### V4

`V4` *extends* `CaseWhenValue`

#### D

`D` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### condition4

`C4`

#### value4

`V4`

#### defaultValue

`D`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`, `V4`, `D`\], `true`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, C4, V4, C5, V5>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
   condition4, 
   value4, 
   condition5, 
value5): CaseWhenResult<[V1, V2, V3, V4, V5], false>;
```

Defined in: [packages/db/src/query/builder/functions.ts:523](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L523)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### C4

`C4` *extends* `ExpressionLike`

#### V4

`V4` *extends* `CaseWhenValue`

#### C5

`C5` *extends* `ExpressionLike`

#### V5

`V5` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### condition4

`C4`

#### value4

`V4`

#### condition5

`C5`

#### value5

`V5`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`, `V4`, `V5`\], `false`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, C4, V4, C5, V5, D>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
   condition4, 
   value4, 
   condition5, 
   value5, 
defaultValue): CaseWhenResult<[V1, V2, V3, V4, V5, D], true>;
```

Defined in: [packages/db/src/query/builder/functions.ts:546](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L546)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### C4

`C4` *extends* `ExpressionLike`

#### V4

`V4` *extends* `CaseWhenValue`

#### C5

`C5` *extends* `ExpressionLike`

#### V5

`V5` *extends* `CaseWhenValue`

#### D

`D` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### condition4

`C4`

#### value4

`V4`

#### condition5

`C5`

#### value5

`V5`

#### defaultValue

`D`

### Returns

`CaseWhenResult`\<\[`V1`, `V2`, `V3`, `V4`, `V5`, `D`\], `true`\>

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```

## Call Signature

```ts
function caseWhen<C1, V1, C2, V2, C3, V3, C4, V4, C5, V5>(
   condition1, 
   value1, 
   condition2, 
   value2, 
   condition3, 
   value3, 
   condition4, 
   value4, 
   condition5, 
   value5, 
   condition6, 
   value6, ...
   rest): any;
```

Defined in: [packages/db/src/query/builder/functions.ts:571](https://github.com/TanStack/db/blob/main/packages/db/src/query/builder/functions.ts#L571)

Returns the value for the first matching condition, similar to SQL
`CASE WHEN`.

Arguments are evaluated as condition/value pairs followed by an optional
default value. Scalar branch values return a query expression and can be used
in expression contexts like `select`, `where`, `orderBy`, `groupBy`,
`having`, and equality join operands. If no scalar branch matches and no
default is provided, the result is `null`.

When a branch value is a projection object, `caseWhen` becomes a select-only
projection value. Projection branches can include nested fields, ref spreads,
and includes. If no projection branch matches and no default is provided, the
result is `undefined`.

### Type Parameters

#### C1

`C1` *extends* `ExpressionLike`

#### V1

`V1` *extends* `CaseWhenValue`

#### C2

`C2` *extends* `ExpressionLike`

#### V2

`V2` *extends* `CaseWhenValue`

#### C3

`C3` *extends* `ExpressionLike`

#### V3

`V3` *extends* `CaseWhenValue`

#### C4

`C4` *extends* `ExpressionLike`

#### V4

`V4` *extends* `CaseWhenValue`

#### C5

`C5` *extends* `ExpressionLike`

#### V5

`V5` *extends* `CaseWhenValue`

### Parameters

#### condition1

`C1`

#### value1

`V1`

#### condition2

`C2`

#### value2

`V2`

#### condition3

`C3`

#### value3

`V3`

#### condition4

`C4`

#### value4

`V4`

#### condition5

`C5`

#### value5

`V5`

#### condition6

`ExpressionLike`

#### value6

`CaseWhenValue`

#### rest

...`CaseWhenValue`[]

### Returns

`any`

### Examples

```ts
caseWhen(gt(user.age, 18), `adult`, `minor`)
```

```ts
caseWhen(
  gt(user.age, 65),
  `senior`,
  gt(user.age, 18),
  `adult`,
  `minor`,
)
```

```ts
caseWhen(gt(user.age, 18), {
  ...user,
  posts: q
    .from({ post: postsCollection })
    .where(({ post }) => eq(post.userId, user.id)),
})
```
