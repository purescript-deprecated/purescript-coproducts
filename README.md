# Module Documentation

## Module Data.Functor.Coproduct

#### `Coproduct`

``` purescript
newtype Coproduct f g a
  = Coproduct (Either (f a) (g a))
```


#### `runCoproduct`

``` purescript
runCoproduct :: forall f g a. Coproduct f g a -> Either (f a) (g a)
```


#### `left`

``` purescript
left :: forall f g a. f a -> Coproduct f g a
```


#### `right`

``` purescript
right :: forall f g a. g a -> Coproduct f g a
```


#### `coproduct`

``` purescript
coproduct :: forall f g a b. (f a -> b) -> (g a -> b) -> Coproduct f g a -> b
```


#### `functorCoproduct`

``` purescript
instance functorCoproduct :: (Functor f, Functor g) => Functor (Coproduct f g)
```


#### `foldableCoproduct`

``` purescript
instance foldableCoproduct :: (Foldable f, Foldable g) => Foldable (Coproduct f g)
```


#### `traversableCoproduct`

``` purescript
instance traversableCoproduct :: (Traversable f, Traversable g) => Traversable (Coproduct f g)
```