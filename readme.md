
# eloquent-eager-loading

$posts = App\Post::all();
$posts->map(function ($post) { return $post->author; });

$posts = App\Post::with('author')->get();
$posts->map(function ($post) { return $post->author; });

$posts = App\Post::with([‘author', 'comments'])->get();

$posts = App\Post::with('author')->get();
$posts->map(function ($post) { return $post->author->profile;});

$posts = App\Post::with('author.profile')->get();
$posts->map(function ($post) { return $post->author->profile;});

$posts = App\Post::all();
$posts->load('author.profile');
$posts->first()->author->profile;
