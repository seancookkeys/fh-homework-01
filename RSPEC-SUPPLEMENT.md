# Homework #01 - Supplement

## Steps To Follow

1.  run all the specs

```
$ rspec
```

generates a list of commands for the failing specs:

```
rspec ./spec/controllers/authors_controller_spec.rb:41 # AuthorsController POST #create with valid params creates a new Author
rspec ./spec/controllers/authors_controller_spec.rb:47 # AuthorsController POST #create with valid params assigns a newly created author as @author
rspec ./spec/controllers/authors_controller_spec.rb:53 # AuthorsController POST #create with valid params redirects to the created author
rspec ./spec/controllers/authors_controller_spec.rb:60 # AuthorsController POST #create with invalid params assigns a newly created but unsaved author as @author
rspec ./spec/controllers/authors_controller_spec.rb:66 # AuthorsController POST #create with invalid params re-renders the 'new' template
rspec ./spec/controllers/authors_controller_spec.rb:79 # AuthorsController PUT #update with valid params updates the requested author
rspec ./spec/controllers/authors_controller_spec.rb:85 # AuthorsController PUT #update with valid params assigns the requested author as @author
rspec ./spec/controllers/authors_controller_spec.rb:91 # AuthorsController PUT #update with valid params redirects to the author
rspec ./spec/controllers/authors_controller_spec.rb:99 # AuthorsController PUT #update with invalid params assigns the author as @author
rspec ./spec/controllers/authors_controller_spec.rb:105 # AuthorsController PUT #update with invalid params re-renders the 'edit' template
rspec ./spec/controllers/authors_controller_spec.rb:114 # AuthorsController DELETE #destroy destroys the requested author
rspec ./spec/controllers/authors_controller_spec.rb:121 # AuthorsController DELETE #destroy redirects to the authors list
rspec ./spec/views/authors/edit.html.erb_spec.rb:12 # authors/edit renders the edit author form
rspec ./spec/views/authors/new.html.erb_spec.rb:12 # authors/new renders new author form
```

2.  pick one of the commands from step (1)

```
rspec ./spec/controllers/authors_controller_spec.rb:41
```

generates the following output

```
F

Failures:

  1) AuthorsController POST #create with valid params creates a new Author
     Failure/Error: post :create, params: {author: valid_attributes}, session: valid_session

     AbstractController::ActionNotFound:
       The action 'create' could not be found for AuthorsController
     # ./spec/controllers/authors_controller_spec.rb:43:in `block (5 levels) in <top (required)>'
     # ./spec/controllers/authors_controller_spec.rb:42:in `block (4 levels) in <top (required)>'

Finished in 0.18864 seconds (files took 1.91 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/controllers/authors_controller_spec.rb:41 # AuthorsController POST #create with valid params creates a new Author
```

3.  read and the understand the error

The error from step (2) tells us the following important bit of information:

```
AbstractController::ActionNotFound:
     The action 'create' could not be found for AuthorsController
```

Note: This simply means that there isn't an action called `create` within the `authors_controller.rb`
file.

4.  fix the code base on the error in step (3)

On line 26, rename

```
def creates
```

to

```
def create
```

Note: The seven default actions for a Rails controller are as follows:

      index, new, create, show, edit, update, and destroy

5.  rerun the current spec selected in step (2)

```
rspec ./spec/controllers/authors_controller_spec.rb:41
```

If you have correctly implemented the code which makes the example/test pass, then you should see
the following:

```
.

Finished in 0.02935 seconds (files took 1.9 seconds to load)
1 example, 0 failures
```

Note: That this should will display a green dot indicating the example/test has passed. Also, you'll
see the failures equal to 0.

6.  now you ready to locate the next failure

Go to step (1)

Note: You'll repeat these steps until there are no failures.

## Closing thoughts

If you have any questions regarding the information presented here, please do send me a message
via Slack at your earliest.
