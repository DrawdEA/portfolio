<script>
  // The email address to be copied
  let email = "edwardjoshua.diesta@gmail.com";

  // Reactive state variables
  let copied = false;
  let tooltipText = "Copy email";

  // This function handles the click event
  const copyEmail = async () => {
      // Prevent running again if already in "copied" state
      if (copied) return;

      try {
      await navigator.clipboard.writeText(email);

      // --- Success State ---
      copied = true;
      tooltipText = "Copied!";

      // Reset the state after 2 seconds
      setTimeout(() => {
          copied = false;
          tooltipText = "Copy email";
      }, 2000);
      } catch (err) {
      // --- Error State ---
      console.error("Failed to copy email: ", err);
      tooltipText = "Copy failed!";

      // Reset the tooltip text after 2 seconds
      setTimeout(() => {
          tooltipText = "Copy email";
      }, 2000);
      }
  };
</script>

<footer class="w-full py-8 flex justify-center bg-transparent text-gray-400" id="footer">
  <div class="w-full max-w-5xl flex flex-col items-center gap-4 sm:flex-row sm:justify-between px-6">
    <p class="text-center sm:text-left text-base font-bold ">
      &copy; {new Date().getFullYear()} Edward Joshua Diesta. All Rights Reserved.
    </p>
    <nav aria-label="Social media links">
      <ul class="flex items-center gap-5">
        <li>
          <a
            href="https://github.com/DrawdEA"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub"
            class="hover:text-white transition-colors"
          >
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="36px" height="36px" viewBox="0 0 32 32" fill="currentColor">
            <path fill-rule="evenodd" d="M 16 4 C 9.371094 4 4 9.371094 4 16 C 4 21.300781 7.4375 25.800781 12.207031 27.386719 C 12.808594 27.496094 13.027344 27.128906 13.027344 26.808594 C 13.027344 26.523438 13.015625 25.769531 13.011719 24.769531 C 9.671875 25.492188 8.96875 23.160156 8.96875 23.160156 C 8.421875 21.773438 7.636719 21.402344 7.636719 21.402344 C 6.546875 20.660156 7.71875 20.675781 7.71875 20.675781 C 8.921875 20.761719 9.554688 21.910156 9.554688 21.910156 C 10.625 23.746094 12.363281 23.214844 13.046875 22.910156 C 13.15625 22.132813 13.46875 21.605469 13.808594 21.304688 C 11.144531 21.003906 8.34375 19.972656 8.34375 15.375 C 8.34375 14.0625 8.8125 12.992188 9.578125 12.152344 C 9.457031 11.851563 9.042969 10.628906 9.695313 8.976563 C 9.695313 8.976563 10.703125 8.65625 12.996094 10.207031 C 13.953125 9.941406 14.980469 9.808594 16 9.804688 C 17.019531 9.808594 18.046875 9.941406 19.003906 10.207031 C 21.296875 8.65625 22.300781 8.976563 22.300781 8.976563 C 22.957031 10.628906 22.546875 11.851563 22.421875 12.152344 C 23.191406 12.992188 23.652344 14.0625 23.652344 15.375 C 23.652344 19.984375 20.847656 20.996094 18.175781 21.296875 C 18.605469 21.664063 18.988281 22.398438 18.988281 23.515625 C 18.988281 25.121094 18.976563 26.414063 18.976563 26.808594 C 18.976563 27.128906 19.191406 27.503906 19.800781 27.386719 C 24.566406 25.796875 28 21.300781 28 16 C 28 9.371094 22.628906 4 16 4 Z"></path>
        </svg>
          </a>
        </li>
        <li>
          <a
            href="https://www.facebook.com/edwardjoshua.diesta/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="Facebook"
            class="hover:text-white transition-colors"
          >
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="36px" height="36px" viewBox="0 0 32 32" fill="currentColor">
            <path d="M 16 4 C 9.3844276 4 4 9.3844276 4 16 C 4 22.615572 9.3844276 28 16 28 C 22.615572 28 28 22.615572 28 16 C 28 9.3844276 22.615572 4 16 4 z M 16 6 C 21.534692 6 26 10.465308 26 16 C 26 21.027386 22.311682 25.161277 17.488281 25.878906 L 17.488281 18.916016 L 20.335938 18.916016 L 20.783203 16.023438 L 17.488281 16.023438 L 17.488281 14.443359 C 17.488281 13.242359 17.882859 12.175781 19.005859 12.175781 L 20.810547 12.175781 L 20.810547 9.6523438 C 20.493547 9.6093438 19.822688 9.515625 18.554688 9.515625 C 15.906688 9.515625 14.355469 10.913609 14.355469 14.099609 L 14.355469 16.023438 L 11.632812 16.023438 L 11.632812 18.916016 L 14.355469 18.916016 L 14.355469 25.853516 C 9.6088556 25.070647 6 20.973047 6 16 C 6 10.465308 10.465308 6 16 6 z"></path>
        </svg>
          </a>
        </li>
        <li>
          <a
            href="https://www.instagram.com/d_rawde/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="Instagram"
            class="hover:text-white transition-colors"
          >
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="36px" height="36px" viewBox="0 0 32 32" fill="currentColor">
            <path d="M 11.46875 5 C 7.917969 5 5 7.914063 5 11.46875 L 5 20.53125 C 5 24.082031 7.914063 27 11.46875 27 L 20.53125 27 C 24.082031 27 27 24.085938 27 20.53125 L 27 11.46875 C 27 7.917969 24.085938 5 20.53125 5 Z M 11.46875 7 L 20.53125 7 C 23.003906 7 25 8.996094 25 11.46875 L 25 20.53125 C 25 23.003906 23.003906 25 20.53125 25 L 11.46875 25 C 8.996094 25 7 23.003906 7 20.53125 L 7 11.46875 C 7 8.996094 8.996094 7 11.46875 7 Z M 21.90625 9.1875 C 21.402344 9.1875 21 9.589844 21 10.09375 C 21 10.597656 21.402344 11 21.90625 11 C 22.410156 11 22.8125 10.597656 22.8125 10.09375 C 22.8125 9.589844 22.410156 9.1875 21.90625 9.1875 Z M 16 10 C 12.699219 10 10 12.699219 10 16 C 10 19.300781 12.699219 22 16 22 C 19.300781 22 22 19.300781 22 16 C 22 12.699219 19.300781 10 16 10 Z M 16 12 C 18.222656 12 20 13.777344 20 16 C 20 18.222656 18.222656 20 16 20 C 13.777344 20 12 18.222656 12 16 C 12 13.777344 13.777344 12 16 12 Z"></path>
        </svg>
          </a>
        </li>
        <li>
          <a
        href="https://www.linkedin.com/in/edward-joshua-diesta-263132233/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn"
            class="hover:text-white transition-colors"
          >
            <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="36px" height="36px" viewBox="0 0 32 32" fill="currentColor">
                <path d="M 7.5 5 C 6.132813 5 5 6.132813 5 7.5 L 5 24.5 C 5 25.867188 6.132813 27 7.5 27 L 24.5 27 C 25.867188 27 27 25.867188 27 24.5 L 27 7.5 C 27 6.132813 25.867188 5 24.5 5 Z M 7.5 7 L 24.5 7 C 24.785156 7 25 7.214844 25 7.5 L 25 24.5 C 25 24.785156 24.785156 25 24.5 25 L 7.5 25 C 7.214844 25 7 24.785156 7 24.5 L 7 7.5 C 7 7.214844 7.214844 7 7.5 7 Z M 10.4375 8.71875 C 9.488281 8.71875 8.71875 9.488281 8.71875 10.4375 C 8.71875 11.386719 9.488281 12.15625 10.4375 12.15625 C 11.386719 12.15625 12.15625 11.386719 12.15625 10.4375 C 12.15625 9.488281 11.386719 8.71875 10.4375 8.71875 Z M 19.46875 13.28125 C 18.035156 13.28125 17.082031 14.066406 16.6875 14.8125 L 16.625 14.8125 L 16.625 13.5 L 13.8125 13.5 L 13.8125 23 L 16.75 23 L 16.75 18.3125 C 16.75 17.074219 16.996094 15.875 18.53125 15.875 C 20.042969 15.875 20.0625 17.273438 20.0625 18.375 L 20.0625 23 L 23 23 L 23 17.78125 C 23 15.226563 22.457031 13.28125 19.46875 13.28125 Z M 9 13.5 L 9 23 L 11.96875 23 L 11.96875 13.5 Z"></path>
            </svg>
          </a>
        </li>
        <li class="flex items-center pl-2">
          <!-- The `relative` class is removed, and `flex items-center` is added -->
          <button
              on:click={copyEmail}
              aria-label="Copy email address"
              class="group transition-colors hover:text-white"
          >
              {#if copied}
              <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="28px"
                  height="28px"
                  viewBox="0 -960 960 960"
                  fill="currentColor"
                  
              >
                  <path d="M382-240 154-468l57-57 171 171 367-367 57 57z" />
              </svg>
              {:else}
              <!-- Default Icon: Mail -->
              <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="28px"
                  height="28px"
                  viewBox="0 -960 960 960"
                  fill="currentColor"
                  class="block group-hover:hidden"
              >
                  <path
                  d="M160-160q-33 0-56.5-23.5T80-240v-480q0-33 23.5-56.5T160-800h640q33 0 56.5 23.5T880-720v480q0 33-23.5 56.5T800-160zm320-280L160-640v400h640v-400zm0-80 320-200H160zM160-640v-80 480z"
                  />
              </svg>
              <!-- Hover Icon: Copy -->
              <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="28px"
                  height="28px"
                  viewBox="0 -960 960 960"
                  fill="currentColor"
                  class="hidden group-hover:block"
              >
                  <path
                  d="M360-240q-33 0-56.5-23.5T280-320v-480q0-33 23.5-56.5T360-880h360q33 0 56.5 23.5T800-800v480q0 33-23.5 56.5T720-240zm0-80h360v-480H360zM200-80q-33 0-56.5-23.5T120-160v-560h80v560h440v80zm160-240v-480z"
                  />
              </svg>
              {/if}
          </button>
          </li>

          <!-- Portfolio / Resume Link -->
          <li class="pl-2">
          <a
              href="/resume.pdf"
              download="EdwardDiesta_Resume.pdf"
              aria-label="Download Portfolio"
              class="group transition-colors hover:text-white"
          >
              <!-- Default Icon: Portfolio -->
              <svg
              xmlns="http://www.w3.org/2000/svg"
              width="28px"
              height="28px"
              viewBox="0 -960 960 960"
              fill="currentColor"
              class="block group-hover:hidden"
              >
              <path
                  d="M480-240q-56 0-107 17.5T280-170v10h400v-10q-42-35-93-52.5T480-240m0-80q69 0 129 21t111 59v-560H240v560q51-38 111-59t129-21m0-160q-25 0-42.5-17.5T420-540t17.5-42.5T480-600t42.5 17.5T540-540t-17.5 42.5T480-480M240-80q-33 0-56.5-23.5T160-160v-640q0-33 23.5-56.5T240-880h480q33 0 56.5 23.5T800-800v640q0 33-23.5 56.5T720-80zm240-320q58 0 99-41t41-99-41-99-99-41-99 41-41 99 41 99 99 41m0-140"
              />
              </svg>
              <!-- Hover Icon: Download -->
              <svg
              xmlns="http://www.w3.org/2000/svg"
              width="28px"
              height="28px"
              viewBox="0 -960 960 960"
              fill="currentColor"
              class="hidden group-hover:block"
              >
              <path
                  d="M480-320 280-520l56-58 104 104v-326h80v326l104-104 56 58zM240-160q-33 0-56.5-23.5T160-240v-120h80v120h480v-120h80v120q0 33-23.5 56.5T720-160z"
              />
              </svg>
          </a>
          </li>
      </ul>
    </nav>
  </div>
</footer>