# Keymaps

## General mapping
    - Better window navigation
      - "<C-h>" :: move right window
      - "<C-j>" :: move down window
      - "<C-k>" :: move up window
      - "<C-l>" :: move left window

    - Resize with arrows
      - "<C-Up>", ":resize -2<CR>"
      - "<C-Down>", ":resize +2<CR>"
      - "<C-Left>", ":vertical resize -2<CR>"
      - "<C-Right>", ":vertical resize +2<CR>"

    - Navigate buffers
      - "<S-l>", ":bnext<CR>"
      - "<S-h>", ":bprevious<CR>"
    
    - Move text up and down
      - "<A-k>", "<Esc>:m .-2<CR>==gi"
      - "<A-j>", "<Esc>:m .+1<CR>==gi"
    
    - QUIT, close buffers, etc
      - "<leader>q", "<cmd>qa<cr>"
      - "<leader>x", "<cmd>q!<cr>"
      - "<leader>d", "<cmd>Sayonara<cr>"
    
    - Save buffer
      - "<leader>w", "<cmd>w<cr>"
    
    - Insert --
    - Press jk fast to exit insert mode
      - keymap("i", "jk", "<ESC>", opts)
    
    - Visual --
    - Stay in indent mode
      - "<", "<gv"
      - ">", ">gv"
    
    - Move text up and down
      - "<A-j>", ":m .+1<CR>=="
      - "<A-k>", ":m .-2<CR>=="
      - "p", '"_dP'
    
    - Visual Block --
    - Move text up and down
      - "<A-j>", ":move '>+1<CR>gv-gv"
      - "<A-k>", ":move '<-2<CR>gv-gv"
    
    - Noclipboard
      - <leader>vd :: noclipboard delete
    - Custom
      - toggle bool word - true/false
        - "gtb" :: toggle boolean
      
      - clear nvim-notify notifications history
        - "<leader>cn" :: clear notification history
        - "<leader>ti" :: current datetime
      
      - yank all in buffer
        - "<leader>a", ":%y<cr>"
      
      - bufferline
        - "<leader>gb", "<cmd>BufferLinePick<cr>"

      - Neogit
        - <leader>gs :: neogit

## Neovim::

- ### Treesiter
    - #### Refactor
        - grr

- ### Sneak
    - #### repeat motion
        - ";", "<Plug>Sneak_;"
        -  [[\]], "<Plug>Sneak_,"

- ### LSP
    - "gD", "<cmd>lua vim.lsp.buf.declaration()<CR>"
    - "gd", '<cmd>lua require"telescope.builtin".lsp_definitions()<CR>'
    - "K", "<cmd>lua vim.lsp.buf.hover()<CR>"
    - "gi", '<cmd>lua require"telescope.builtin".lsp_implementations()<CR>'
    - "gS", "<cmd>lua vim.lsp.buf.signature_help()<CR>"
    - "gtd", "<cmd>lua vim.lsp.buf.type_definition()<CR>"
    - "<leader>rn", "<cmd>lua vim.lsp.buf.rename()<CR>"
    - "gr", '<cmd>lua require"telescope.builtin".lsp_references()<CR>'
    - "gA", "<cmd>lua vim.lsp.buf.code_action()<CR>"
    - "gA", "<cmd>lua vim.lsp.buf.range_code_action()<CR>"
    - "]e", '<cmd>lua vim.diagnostic.goto_next { float = {scope = "line"} }<cr>'
    - "[e", '<cmd>lua vim.diagnostic.goto_prev { float = {scope = "line"} }<cr>'
    - "<leader>f", "<cmd>lua vim.lsp.buf.formatting() <cr>"
    - vim.cmd [[ command! Format execute 'lua vim.lsp.buf.formatting()' ]]

- ### GitSigns
    - Navigation
      - "]c", "&diff ? ']c' : '<cmd>Gitsigns next_hunk<CR>'"
      - "[c", "&diff ? '[c' : '<cmd>Gitsigns prev_hunk<CR>'"

    - Actions
      - "<leader>hs", gs.stage_hunk)
      - "<leader>hr", gs.reset_hunk)
      - "<leader>hS", gs.stage_buffer)
      - "<leader>hu", gs.undo_stage_hunk)
      - "<leader>hR", gs.reset_buffer)
      - "<leader>hp", gs.preview_hunk)
      - "<leader>hb", function() gs.blame_line { full = true } end)
      - ",tb", gs.toggle_current_line_blame)
      - "<leader>hd", gs.diffthis)
      - "<leader>hD", function() gs.diffthis "~" end)
      - ",td", function() gs.toggle_deleted() gs.toggle_word_diff()  end)
      - "<leader>hn", gs.toggle_numhl)
      - "<leader>hh", gs.toggle_linehl)

    - Hunk Text Object
      - "ih", ":<C-U>Gitsigns select_hunk<CR>")

- ### CMP
    ["<C-b>"] = cmp.mapping(cmp.mapping.scroll_docs(-4), { "i", "c" }),
    ["<C-f>"] = cmp.mapping(cmp.mapping.scroll_docs(4), { "i", "c" }),
    ["<C-Space>"] = cmp.mapping(cmp.mapping.complete(), { "i", "c" }),
    ["<C-y>"] = cmp.config.disable, -- Specify `cmp.config.disable` if you want to remove the default `<C-y>` mapping.
    ["<C-e>"] = cmp.mapping { i = cmp.mapping.abort(),c = cmp.mapping.close(),},

- ### Registers
    - " open normal mode
    - <c-r> open insert mode
    - <c-j> nav down
    - <c-k> nav up

- ### Vim Sandwich
    - saiw "({"
    - vsa "({ down" )}
    - saiwi text text
    - <c-v>#j#lsa ("{")
    - <c-v>#j$sa ("{")
    -  #saiw("{")
    -  srb replace
    -  sdb delete

- ### Targets
    - #cin )"]
    - da,
    - #ca )"}"
    - #cI )"}"
    - #ca )}""
    - #ci'
    - #ca'
    - cia
    - caa

- ### Comment
    - gc line
    - gb block

- ### Telescope
    - Navigate buffers and repos
      - "<c-p>", [[<cmd>Telescope commands theme=get_dropdown<cr>]]
      - "<c-a>", [[<cmd>Telescope buffers show_all_buffers=true theme=get_dropdown<cr>]]
      - "<c-e>", [[<cmd>Telescope frecency theme=get_dropdown<cr>]]
      - "<c-s>", [[<cmd>Telescope git_files theme=get_dropdown<cr>]
      - "<c-d>", [[<cmd>Telescope find_files theme=get_dropdown<cr>)
      - "<c-g>", [[<cmd>Telescope live_grep theme=get_dropdown<cr>]

    - Notify
      - <leader>nh :: open notifys

    - command palette
      - "<space>k", [[<Cmd>:Telescope command_palette<CR>]]
    
    - neoclip
      - "<C-n>", [[<Cmd>lua require('telescope').extensions.neoclip.default()<CR>]]

## I3
  - mod + enter :: terminal
  - mod + d :: dmenu
  - mod + v :: split horizontal
  - mod + f :: fullscreen
  - mod + shift + q :: close app
  - mod + # :: new window
  - mod + shift + # :: move app to window
  - mod + shift + e :: close session
  - mod + shift + r :: reload 
  - mod + shift + c :: reload config
  - mod + w :: tabbed 
  - mod + e :: vertical or horizontal layout
  - mod + s :: stacked layout

## TMUX
  - PREFIX(CTRL + a)
    - Window
      - prefix + c : new window
      - prefix + w : list windows
      - prefix + n : next window
      - prefix + p : previous window
      - prefix + f : find window
      - prefix + & : kill window
      - prefix + , : rename
      - prefix + number : move to # window
      - prefix + shift + 1 : move panel to new window
      - prefix + shift + : : move window to pane(join-pane -s # -t #)
      - prefix + shift + : : change window order(swap-window -s # -t #)
      - prefix + : maximeze panel to a new window
      - prefix ctrl h : previous window
      - prefix ctrl b : next window
      - prefix tab : last window

    - Panel
      - prefix + % : vertical split
      - prefix + " : horizontal split
      - prefix + q : show panel number
      - prefix + + : pane into window
      - prefix + - : restore pane window
      - prefix + x : kill pane
      - prefix + space : change vertical/horizontal
      - prefix + { } : alternate pane
      - prefix + arrows : move to panel
      - prefix + ctrl + o : move all panel anti clock
      - prefix + o : move to panel sentido horario
      - prefix + hold ctrl + arrows : rezise pane
      - prefix h - j - k - l : navegate panels
      - prefix H - J - K -L : rezise panels
      - prefix > - < : swap panel

    - Session
      - prefix ctrl c : create new session
      - prefix ctrl f : find session 
      - prefix + d : detach session

    - Copy mode
      - prefix enter : copy mode
      - prefix b : list buffer copies
      - prefix p : paste
      - prefix P : chose what to paste

    - Others
      - prefix + z : toggle full screen
      - ctrl + s : search word
      - prefix m : toogle mouse 

## Ranger
  - q : QUIT
  - i : display
  - W : display log
  - w : tasks view
  - S : go to shell
  - : console
  - ; console
  -  s  console shell%space
  -  r  chain draw_possible_programs; console open_with%space
  -  f  console find%space
  -  cd console cd%space
  -  <C-p> : ultimo comando de la consola
  - M : informacion de los archivos
  - t : tag-toggle
  - " : any tag
  - space : select cursor
  - v : select all
  - V : visual mode
  - u : remove things
  - F1 :help
  - F2: rename
  - F3 : display
  - F4 : edit
  - F5 : copy
  - F6 : cut
  - F7 : console mkdir
  - F8 : console delete
  - F10 : exit
  - g : go to folder
  - bg : set feh background
  - yy : copy
  - uy : uncut
  - ya : copy mode add
  - yr : copy mode remove
  - yt : copy mode toogle
  - dgg : cut cursor and all top
  - dG : cut cursor and all bottom
  - dj : cut cursor and one bottom
  - dk : cut cursor and one top
  - ygg - yG - yj - yk : same commands cut but instead copy
  - / : console search
  - n : search next 
  - N : search before
  - c : commands to search with some order
  - gn : new tab
  - gc : close tab
  - uq : restore tab
  - gt : move next tab
  - gT : move before tab
  - ALT + # : move to # tab
  - ALT + r : change +1 number tab
  - ALT + l : change -1 number tab
  - o : commands to sorting
  - z : commands to settings
