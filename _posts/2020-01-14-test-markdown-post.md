---
toc: true
layout: post
description: A minimal example of using markdown with fastpages.
categories: [markdown]
title: An Example Markdown Post
---
# Example Markdown Post

```haskell
data HandlerType method model event m a where
    Query :: (CanMutate method ~ 'False, GetModelAccess method ~ 'Direct)
          => (model -> m a)
          -> HandlerType method model event m a
    CbQuery :: (CanMutate method ~ 'False, GetModelAccess method ~ 'Callback)
          => ((m model) -> m a)
          -> HandlerType method model event m a
    Cmd :: ( CanMutate method ~ 'True, GetModelAccess method ~ 'Direct)
        => (model -> m (model -> a, [event]))
        -> HandlerType method model event m a
    CbCmd :: ( CanMutate method ~ 'True, GetModelAccess method ~ 'Callback)
        => ((forall x. (model -> m (model -> x, [event])) -> m x) -> m a)
        -> HandlerType method model event m a
```
