# Keymaps

## General mapping
    - Better window navigation
      - keymap("n", "<C-h>", "<C-w>h", opts)
      - keymap("n", "<C-j>", "<C-w>j", opts)
      - keymap("n", "<C-k>", "<C-w>k", opts)
      - keymap("n", "<C-l>", "<C-w>l", opts)

    - Resize with arrows
      - keymap("n", "<C-Up>", ":resize -2<CR>", opts)
      - keymap("n", "<C-Down>", ":resize +2<CR>", opts)
      - keymap("n", "<C-Left>", ":vertical resize -2<CR>", opts)
      - keymap("n", "<C-Right>", ":vertical resize +2<CR>", opts)

    -- Navigate buffers:CHECK
      - keymap("n", "<S-l>", ":bnext<CR>", opts)
      - keymap("n", "<S-h>", ":bprevious<CR>", opts)
    
    - Move text up and down
      - keymap("n", "<A-k>", "<Esc>:m .-2<CR>==gi", opts)
      - keymap("n", "<A-j>", "<Esc>:m .+1<CR>==gi", opts)
    
    - QUIT, close buffers, etc
      - keymap("n", "<leader>q", "<cmd>qa<cr>", opts)
      - keymap("n", "<leader>x", "<cmd>q!<cr>", opts)
      - keymap("n", "<leader>d", "<cmd>Sayonara<cr>", { silent = true, nowait = true, noremap = true })
    
    - Save buffer
      - keymap("n", "<leader>w", "<cmd>w<cr>", opts)
    
    - Version Control : git
      - keymap("n", "gs", "<cmd>Neogit<cr>", opts)
    
    - Insert --
    - Press jk fast to exit insert mode
      - keymap("i", "jk", "<ESC>", opts)
    
    - Save buffer
      - keymap("i", "<c-s>", "<esc><cmd>w<cr>a", opts)
    
    - Visual --
    - Stay in indent mode
      - keymap("v", "<", "<gv", opts)
      - keymap("v", ">", ">gv", opts)
    
    - Move text up and down
      - keymap("v", "<A-j>", ":m .+1<CR>==", opts)
      - keymap("v", "<A-k>", ":m .-2<CR>==", opts)
      - keymap("v", "p", '"_dP', opts)
    
    - Visual Block --
    - Move text up and down
      - keymap("x", "J", ":move '>+1<CR>gv-gv", opts)
      - keymap("x", "K", ":move '<-2<CR>gv-gv", opts)
      - keymap("x", "<A-j>", ":move '>+1<CR>gv-gv", opts)
      - keymap("x", "<A-k>", ":move '<-2<CR>gv-gv", opts)
    
    -nvim tree
      - keymap("n", "<leader>n", ":NvimTreeToggle<cr>", opts)
    
    - Custom
    
      - toggle bool word - true/false
        - keymap("n","gtb",":lua require('funcs').toggle_bool({word=vim.fn.expand('<cword>')})<CR>",{ noremap = true, silent = true })
        - keymap("v", "<leader>t", [[<Cmd>lua require'funcs'.create_todoist_task()<CR>]], { noremap = false })
      
      - clear nvim-notify notifications history
        - keymap("n", "<leader>cn", ":lua require('funcs').clear_notification_history()<CR>", { noremap = true, silent = true })
        - keymap("n", "<leader>ti", ":lua require('funcs').notify_current_datetime()<CR>", { noremap = true, silent = true })
        - keymap("n", "<leader>gf", ":vs <cfile><CR>", { noremap = false, silent = true })
        - keymap("n", "<leader>t", ":TSHighlightCapturesUnderCursor<CR>", { noremap = true, silent = true })
      
      - toggle neoclip - https://github.com/AckslD/nvim-neoclip.lua#startstop
        - keymap("n", ",tn", [[<Cmd>lua require('neoclip').toggle()<CR>]], { noremap = true, silent = true })
      
      - open new Neovim Terminal in vsplit or split
        - keymap("n", "<leader>tv", [[<Cmd>vsp <bar>terminal<CR>]], { noremap = false, silent = true })
      
      - open short terminal at the bottom of the buffer
        - keymap("n", "<leader>ts", [[<Cmd>11sp <bar>terminal<CR>]], { noremap = false, silent = true })
      
      - open lazygit in vert split - custom lazygit config uses ctrl-x as menu close
        - --keymap("n", "<space>lg", [[<Cmd>135vsp <bar>terminal lazygit<CR>]], { noremap = true, silent = true })
      
      - yank all in buffer
        - keymap("n", "<leader>a", ":%y<cr>", { noremap = false, silent = true })
      
      - bufferline
        - map("n", "<leader>gb", "<cmd>BufferLinePick<cr>", opts)

## Neovim::

- ### Treesiter
    - #### Incremental selection
        - init_selection = "<CR>",
        - scope_incremental = "<CR>",
        - node_incremental = "<TAB>",
        - node_decremental = "<S-TAB>",
    - #### Refactor
        - grr
    - #### Text subjects
        - ["."] = "textsubjects-smart", --comments, consecutive line comments, function calls, function definitions, class definitions, loops, if statements, return values, arguments.
        - [";"] = "textsubjects-container-outer", --Classes, structs, functions, methods.
        - ["i;"] = "textsubjects-container-inner", --Inside Classes, structs, functions, methods.
    - #### Playground
        - toggle_query_editor = "o",
        - toggle_hl_groups = "i",
        - toggle_injected_languages = "t",
        - toggle_anonymous_nodes = "a",
        - toggle_language_display = "I",
        - focus_language = "f",
        - unfocus_language = "F",
        - update = "R",
        - goto_node = "<cr>",
        - show_help = "?",

- ### Sneak
    - map("n", "z", "<Plug>(leap-forward)", opts)
    - map("n", "Z", "<Plug>(leap-backward)", opts)

    - #### visual-mode
        - map("x", "z", "<Plug>(leap-forward)", opts)
        - map("x", "Z", "<Plug>(leap-backward)", opts)
    
    - #### repeat motion
        - map("", ";", "<Plug>Sneak_;", opts)
        - map("", [[\]], "<Plug>Sneak_,", opts)

- ### LSP
    - buf_keymap(bufnr, "n", "gD", "<cmd>lua vim.lsp.buf.declaration()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "gd", '<cmd>lua require"telescope.builtin".lsp_definitions()<CR>', keymap_opts)
    - buf_keymap(bufnr, "n", "K", "<cmd>lua vim.lsp.buf.hover()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "gi", '<cmd>lua require"telescope.builtin".lsp_implementations()<CR>', keymap_opts)
    - buf_keymap(bufnr, "n", "gS", "<cmd>lua vim.lsp.buf.signature_help()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "gtd", "<cmd>lua vim.lsp.buf.type_definition()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "<leader>rn", "<cmd>lua vim.lsp.buf.rename()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "gr", '<cmd>lua require"telescope.builtin".lsp_references()<CR>', keymap_opts)
    - buf_keymap(bufnr, "n", "gA", "<cmd>lua vim.lsp.buf.code_action()<CR>", keymap_opts)
    - buf_keymap(bufnr, "v", "gA", "<cmd>lua vim.lsp.buf.range_code_action()<CR>", keymap_opts)
    - buf_keymap(bufnr, "n", "]e", '<cmd>lua vim.diagnostic.goto_next { float = {scope = "line"} }<cr>', keymap_opts)
    - buf_keymap(bufnr, "n", "[e", '<cmd>lua vim.diagnostic.goto_prev { float = {scope = "line"} }<cr>', keymap_opts)
    - buf_keymap(bufnr, "n", "<leader>f", "<cmd>lua vim.lsp.buf.formatting() <cr>", keymap_opts)
    - vim.cmd [[ command! Format execute 'lua vim.lsp.buf.formatting()' ]]

- ### GitSigns
    - Navigation
      - map("n", "]c", "&diff ? ']c' : '<cmd>Gitsigns next_hunk<CR>'", { expr = true })
      - map("n", "[c", "&diff ? '[c' : '<cmd>Gitsigns prev_hunk<CR>'", { expr = true })

    - Actions
      - map({ "n", "v" }, "<leader>hs", gs.stage_hunk)
      - map({ "n", "v" }, "<leader>hr", gs.reset_hunk)
      - map("n", "<leader>hS", gs.stage_buffer)
      - map("n", "<leader>hu", gs.undo_stage_hunk)
      - map("n", "<leader>hR", gs.reset_buffer)
      - map("n", "<leader>hp", gs.preview_hunk)
      - map("n", "<leader>hb", function() gs.blame_line { full = true } end)
      - map("n", ",tb", gs.toggle_current_line_blame)
      - map("n", "<leader>hd", gs.diffthis)
      - map("n", "<leader>hD", function() gs.diffthis "~" end)
      - map("n", ",td", function() gs.toggle_deleted() gs.toggle_word_diff()  end)
      - map("n", "<leader>hn", gs.toggle_numhl)
      - map("n", "<leader>hh", gs.toggle_linehl)

    - Hunk Text Object
      - map({ "o", "x" }, "ih", ":<C-U>Gitsigns select_hunk<CR>")

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

- ### Neogit
    - gs

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

- ### ToggleTerm
    - <c-\> open

- ### Comment
    - gc line
    - gb block

- ### Telescope
    - Navigate buffers and repos
      -  --map("n", "<c-p>", [[<cmd>Telescope buffers show_all_buffers=true theme=get_dropdown<cr>]], silent)
      - map("n", "<c-p>", [[<cmd>Telescope commands theme=get_dropdown<cr>]], silent)
      - map("n", "<c-a>", [[<cmd>Telescope buffers show_all_buffers=true theme=get_dropdown<cr>]], silent)
      - map("n", "<c-e>", [[<cmd>Telescope frecency theme=get_dropdown<cr>]], silent)
      - map("n", "<c-s>", [[<cmd>Telescope git_files theme=get_dropdown<cr>]], silent)
      - map("n", "<c-d>", [[<cmd>Telescope find_files theme=get_dropdown<cr>]], silent)
      - map("n", "<c-g>", [[<cmd>Telescope live_grep theme=get_dropdown<cr>]], silent)

    - command palette
      - map("n", "<space>k", [[<Cmd>:Telescope command_palette<CR>]], silent)
    
    - Search through your Neovim related todos
      - map("n", "<leader>st", ":lua require'config.telescope.telescope'.search_todos()<CR>", silent)
    
    - search Brave bookmarks & go
      - map("n", "<space>b", [[<Cmd>lua require('telescope').extensions.bookmarks.bookmarks()<CR>]], silent)
    
    - telescope-repo
      - map("n", "<leader>rl", [[<Cmd>lua require'.telescope'.repo_list()<CR>]], silent)
    
    - telescope notify history
      - map("<leader>nh",[<Cmd>lua require('telescope').extensions.notify.notify({results_title='Notification History', prompt_title='Search Messages'})<CR>]],)
    
    - Telescope resume (last picker)
      - map("n", "<leader>tr", [[<Cmd>lua require'telescope.builtin'.resume()<CR>]], silent)

    - git_branches
      - map(";gb",[<Cmd>lua require'telescope.builtin'.git_branches({prompt_title = ' ', results_title='Git Branches'})<CR>]],)
    
    - git_bcommits - file scoped commits with diff preview. <C-V> for vsp diff to parent
      - map("<space>gc",[[<Cmd>lua require'telescope.builtin'.git_bcommits({prompt_title = '  ', results_title='Git File Commits'})<CR>]])

    - git_commits (log) git log
      - map("n", "gl", [[<Cmd>lua require'telescope.builtin'.git_commits()<CR>]], silent)
    
    - git_status - <tab> to toggle staging
      - map("n", "gs", [[<Cmd>lua require'telescope.builtin'.git_status()<CR>]], silent)
    
    - registers picker
      - map("n", "<space>r", [[<Cmd>lua require'telescope.builtin'.registers()<CR>]], silent)
    
    - show Workspace Diagnostics
      - map("n", ",d", [[<Cmd>lua require'telescope.builtin'.diagnostics()<CR>]], silent)
      - map("n", ",k", [[<Cmd>lua require'telescope.builtin'.keymaps({results_title='Key Maps Results'})<CR>]], silent)
      - map("n", ",h", [[<Cmd>lua require'telescope.builtin'.help_tags({results_title='Help Results'})<CR>]], silent)
    
    - find files with gitfiles & fallback on find_files
      - map("n", ",<space>", [[<Cmd>lua require'.telescope'.project_files()<CR>]], silent)
    
    - browse, explore and create notes
      - map("n", ",n", [[<Cmd>lua require'.telescope'.browse_notes()<CR>]], silent)
    
    - Explore files starting at $HOME
      - map("n", ",e", [[<Cmd>lua require'.telescope'.file_explorer()<CR>]], silent)
    
    - Browse files from cwd - File Browser
      - map("n", ",fb", [[<Cmd>lua require'telescope'.extensions.file_browser.file_browser()<CR>]], silent)
    
    - find notes
      - map("n", "<leader>n", [[<Cmd>lua require'.telescope'.find_notes()<CR>]], silent)
    
    - search notes
      - map("n", "<space>n", [[<Cmd>lua require'.telescope'.grep_notes()<CR>]], silent)
    
    - Find files in config dirs
      - map("n", "<space>e", [[<Cmd>lua require'.telescope'.find_configs()<CR>]], silent)
    
    - greg for a string
      - map("n", "<space>g", [[<Cmd>lua require'.telescope'.grep_prompt()<CR>]], silent)
    
    - find or create neovim configs
      - map("n", "<leader>nc", [[<Cmd>lua require'.telescope'.nvim_config()<CR>]], silent)
    
    - Github issues
      - map("n", "<leader>is", [[<Cmd>lua require'.telescope'.gh_issues()<CR>]], silent)
    
    -- github Pull Requests - PRs
      - map("n", "<leader>pr", [[<Cmd>lua require'.telescope'.gh_prs()<CR>]], silent)
    
    - neoclip
      - map("n", "<C-n>", [[<Cmd>lua require('telescope').extensions.neoclip.default()<CR>]], silent)
    
    
