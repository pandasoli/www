<section class='flex flex-col gap-10'>
	<div class='text-center'>
		<h2 class='text-2xl'>My Linux Journey</h2>

		<div class='flex flex-wrap justify-center gap-2 mt-3'>
			<a class='underline text-blue-700' href='https://xubuntu.org'>Xubuntu</a> &gt;
			<a class='underline text-blue-700' href='https://archcraft.io'>ArchCraft</a> &gt;
			<a class='underline text-blue-700' href='https://archlinux.org'>Arch</a> &gt;
			<a class='underline text-blue-700' href='https://gentoo.org'>Gentoo</a> &gt;
			<a class='underline text-blue-700' href='https://kisslinux.github.io'>KISS</a>
		</div>
	</div>

	<div class='px-4 md:px-10'>
		<p>
			A lot of people ask me how I ended up using a such minimal and complicated distro,
			so here's how I did it, step by step.<br>
			<br>
			I'm sure that if you follow this to the letter and are curious to learn on your own,
			you'll be able to get there in the end and use your own distro very easily.
		</p>

		<ul class='flex flex-col gap-3 mt-6 list-disc pl-6'>
			<li>
				<details>
					<summary>
						<b>Xubuntu</b>: Getting used to Linux, seeing how the interface and
						programs work, and having a first contact with the terminal.
					</summary>

					<ul class='list-[circle] pl-6 mt-4'>
						<li>Linux filesystem hierarchy (<code class='bg-gray-200 rounded px-1'>/etc</code>, <code class='bg-gray-200 rounded px-1'>/usr</code>, <code class='bg-gray-200 rounded px-1'>/home</code>, etc.)</li>
						<li>Installing packages with APT</li>
						<li>Working with <code class='bg-gray-200 rounded px-1'>.deb</code> files</li>
						<li>Basic troubleshooting and logs (using GUI and <code class='bg-gray-200 rounded px-1'>dmesg</code>, <code class='bg-gray-200 rounded px-1'>journalctl</code>)</li>
					</ul>
				</details>
			</li>

			<li>
				<details>
					<summary>
						<b>Archcraft</b>: Learning how programs are configured using text files,
						having more terminal interaction, learning commands, and getting used to Arch.
					</summary>

					<ul class='list-[circle] pl-6 mt-4'>
						<li>Window managers (like Openbox, Bspwm)</li>
						<li>Custom theming (GTK, Polybar, etc.)</li>
						<li>Dotfile management</li>
						<li>Scripting small automations (<code class='bg-gray-200 rounded px-1'>bash</code>, <code class='bg-gray-200 rounded px-1'>zsh</code> configs)</li>
					</ul>
				</details>
			</li>

			<li>
				<details>
					<summary>
						<b>Arch</b>: Hardcore experience—installing the full interface from
						scratch, configuring disks.
					</summary>

					<ul class='list-[circle] pl-6 mt-4'>
						<li><code class='bg-gray-200 rounded px-1'>pacman</code> and the AUR</li>
						<li>Manual disk partitioning (e.g. with <code class='bg-gray-200 rounded px-1'>fdisk</code>)</li>
						<li>Writing and maintaining your own config files (e.g. <code class='bg-gray-200 rounded px-1'>/etc/fstab</code>)</li>
						<li>Bootloaders (GRUB, systemd-boot)</li>
					</ul>
				</details>
			</li>

			<li>
				<details>
					<summary>
						<b>Gentoo</b>: Learning about compilation, USE flags, and reading
						documentation.
					</summary>

					<ul class='list-[circle] pl-6 mt-4'>
						<li>Full system customization</li>
						<li>Understanding build systems (autotools, cmake, make)</li>
						<li>Optimizing for your CPU</li>
						<li>Making peace with waiting 😅</li>
					</ul>
				</details>
			</li>

			<li>
				<details>
					<summary>
						<b>KISS</b>: Learning how to configure compilation and strip program
						support to reduce dependencies, working with Wayland, musl, kernel
						configuration, and manually creating an initramfs.
					</summary>

					<ul class='list-[circle] pl-6 mt-4'>
						<li>Minimalism as a design principle</li>
						<li>Writing shell scripts to replace software</li>
						<li>Manual service management (runsv or custom inits)</li>
						<li>Patching and rebuilding programs</li>
						<li>Deep understanding of system internals (init, early boot, static vs dynamic linking)</li>
					</ul>
				</details>
			</li>
		</ul>
	</div>
</section>
