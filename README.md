# Module Documentation

## Module Data.Functor.Coproduct

### Types

    newtype Coproduct f g a where
      Coproduct :: Either (f a) (g a) -> Coproduct f g a


### Type Class Instances

    instance foldableCoproduct :: (Foldable f, Foldable g) => Foldable (Coproduct f g)

    instance functorCoproduct :: (Functor f, Functor g) => Functor (Coproduct f g)

    instance traversableCoproduct :: (Traversable f, Traversable g) => Traversable (Coproduct f g)


### Values

    coproduct :: forall f g a b. (f a -> b) -> (g a -> b) -> Coproduct f g a -> b

    left :: forall f g a. f a -> Coproduct f g a

    right :: forall f g a. g a -> Coproduct f g a

    runCoproduct :: forall f g a. Coproduct f g a -> Either (f a) (g a)