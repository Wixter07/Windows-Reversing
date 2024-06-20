# Position

Ok so we need to find the input name. Fired it on IDA and **sub_401740** is of interest.

```c
int __stdcall sub_401740(int a1)
{
  int v1; // edi
  int v3; // esi
  int v4; // esi
  __int16 v5; // bx
  char v6; // al
  char v7; // al
  unsigned __int8 v8; // bl
  wchar_t *v9; // eax
  __int16 v10; // di
  wchar_t *v11; // eax
  __int16 v12; // di
  wchar_t *v13; // eax
  __int16 v14; // di
  wchar_t *v15; // eax
  __int16 v16; // di
  wchar_t *v17; // eax
  __int16 v18; // di
  char v19; // al
  char v20; // al
  unsigned __int8 v21; // bl
  wchar_t *v22; // eax
  __int16 v23; // di
  wchar_t *v24; // eax
  __int16 v25; // di
  wchar_t *v26; // eax
  __int16 v27; // di
  wchar_t *v28; // eax
  __int16 v29; // di
  wchar_t *v30; // eax
  __int16 v31; // si
  unsigned __int8 v32; // [esp+10h] [ebp-28h]
  unsigned __int8 v33; // [esp+10h] [ebp-28h]
  unsigned __int8 v34; // [esp+11h] [ebp-27h]
  unsigned __int8 v35; // [esp+11h] [ebp-27h]
  unsigned __int8 v36; // [esp+13h] [ebp-25h]
  unsigned __int8 v37; // [esp+13h] [ebp-25h]
  unsigned __int8 v38; // [esp+14h] [ebp-24h]
  unsigned __int8 v39; // [esp+14h] [ebp-24h]
  unsigned __int8 v40; // [esp+18h] [ebp-20h]
  unsigned __int8 v41; // [esp+18h] [ebp-20h]
  unsigned __int8 v42; // [esp+19h] [ebp-1Fh]
  unsigned __int8 v43; // [esp+19h] [ebp-1Fh]
  unsigned __int8 v44; // [esp+1Ah] [ebp-1Eh]
  unsigned __int8 v45; // [esp+1Ah] [ebp-1Eh]
  unsigned __int8 v46; // [esp+1Bh] [ebp-1Dh]
  unsigned __int8 v47; // [esp+1Bh] [ebp-1Dh]
  unsigned __int8 v48; // [esp+1Ch] [ebp-1Ch]
  unsigned __int8 v49; // [esp+1Ch] [ebp-1Ch]
  int v50; // [esp+20h] [ebp-18h] BYREF
  int v51; // [esp+24h] [ebp-14h] BYREF
  char v52[4]; // [esp+28h] [ebp-10h] BYREF
  int v53; // [esp+34h] [ebp-4h]

  mfc100u_296(&v50);
  v1 = 0;
  v53 = 0;
  mfc100u_296(&v51);
  mfc100u_296(v52);
  LOBYTE(v53) = 2;
  mfc100u_7006(a1 + 304, &v50);
  if ( *(_DWORD *)(v50 - 12) == 4 )
  {
    v3 = 0;
    while ( (unsigned __int16)mfc100u_4478(&v50, v3) >= 0x61u && (unsigned __int16)mfc100u_4478(&v50, v3) <= 0x7Au )
    {
      if ( ++v3 >= 4 )
      {
LABEL_7:
        v4 = 0;
        while ( 1 )
        {
          if ( v1 != v4 )
          {
            v5 = mfc100u_4478(&v50, v4);
            if ( (unsigned __int16)mfc100u_4478(&v50, v1) == v5 )
              goto LABEL_2;
          }
          if ( ++v4 >= 4 )
          {
            if ( ++v1 < 4 )
              goto LABEL_7;
            mfc100u_7006(a1 + 420, &v51);
            if ( *(_DWORD *)(v51 - 12) == 11 && (unsigned __int16)mfc100u_4478(&v51, 5) == 45 )
            {
              v6 = mfc100u_4478(&v50, 0);
              v40 = (v6 & 1) + 5;
              v48 = ((v6 & 0x10) != 0) + 5;
              v42 = ((v6 & 2) != 0) + 5;
              v44 = ((v6 & 4) != 0) + 5;
              v46 = ((v6 & 8) != 0) + 5;
              v7 = mfc100u_4478(&v50, 1);
              v32 = (v7 & 1) + 1;
              v38 = ((v7 & 0x10) != 0) + 1;
              v34 = ((v7 & 2) != 0) + 1;
              v8 = ((v7 & 4) != 0) + 1;
              v36 = ((v7 & 8) != 0) + 1;
              v9 = (wchar_t *)mfc100u_4511(v52);
              itow_s(v40 + v8, v9, 0xAu, 10);
              v10 = mfc100u_4478(v52, 0);
              if ( (unsigned __int16)mfc100u_4478(&v51, 0) == v10 )
              {
                mfc100u_11494(v52, -1);
                v11 = (wchar_t *)mfc100u_4511(v52);
                itow_s(v46 + v36, v11, 0xAu, 10);
                v12 = mfc100u_4478(&v51, 1);
                if ( v12 == (unsigned __int16)mfc100u_4478(v52, 0) )
                {
                  mfc100u_11494(v52, -1);
                  v13 = (wchar_t *)mfc100u_4511(v52);
                  itow_s(v42 + v38, v13, 0xAu, 10);
                  v14 = mfc100u_4478(&v51, 2);
                  if ( v14 == (unsigned __int16)mfc100u_4478(v52, 0) )
                  {
                    mfc100u_11494(v52, -1);
                    v15 = (wchar_t *)mfc100u_4511(v52);
                    itow_s(v44 + v32, v15, 0xAu, 10);
                    v16 = mfc100u_4478(&v51, 3);
                    if ( v16 == (unsigned __int16)mfc100u_4478(v52, 0) )
                    {
                      mfc100u_11494(v52, -1);
                      v17 = (wchar_t *)mfc100u_4511(v52);
                      itow_s(v48 + v34, v17, 0xAu, 10);
                      v18 = mfc100u_4478(&v51, 4);
                      if ( v18 == (unsigned __int16)mfc100u_4478(v52, 0) )
                      {
                        mfc100u_11494(v52, -1);
                        v19 = mfc100u_4478(&v50, 2);
                        v41 = (v19 & 1) + 5;
                        v49 = ((v19 & 0x10) != 0) + 5;
                        v43 = ((v19 & 2) != 0) + 5;
                        v45 = ((v19 & 4) != 0) + 5;
                        v47 = ((v19 & 8) != 0) + 5;
                        v20 = mfc100u_4478(&v50, 3);
                        v33 = (v20 & 1) + 1;
                        v39 = ((v20 & 0x10) != 0) + 1;
                        v35 = ((v20 & 2) != 0) + 1;
                        v21 = ((v20 & 4) != 0) + 1;
                        v37 = ((v20 & 8) != 0) + 1;
                        v22 = (wchar_t *)mfc100u_4511(v52);
                        itow_s(v41 + v21, v22, 0xAu, 10);
                        v23 = mfc100u_4478(&v51, 6);
                        if ( v23 == (unsigned __int16)mfc100u_4478(v52, 0) )
                        {
                          mfc100u_11494(v52, -1);
                          v24 = (wchar_t *)mfc100u_4511(v52);
                          itow_s(v47 + v37, v24, 0xAu, 10);
                          v25 = mfc100u_4478(&v51, 7);
                          if ( v25 == (unsigned __int16)mfc100u_4478(v52, 0) )
                          {
                            mfc100u_11494(v52, -1);
                            v26 = (wchar_t *)mfc100u_4511(v52);
                            itow_s(v43 + v39, v26, 0xAu, 10);
                            v27 = mfc100u_4478(&v51, 8);
                            if ( v27 == (unsigned __int16)mfc100u_4478(v52, 0) )
                            {
                              mfc100u_11494(v52, -1);
                              v28 = (wchar_t *)mfc100u_4511(v52);
                              itow_s(v45 + v33, v28, 0xAu, 10);
                              v29 = mfc100u_4478(&v51, 9);
                              if ( v29 == (unsigned __int16)mfc100u_4478(v52, 0) )
                              {
                                mfc100u_11494(v52, -1);
                                v30 = (wchar_t *)mfc100u_4511(v52);
                                itow_s(v49 + v35, v30, 0xAu, 10);
                                v31 = mfc100u_4478(&v51, 10);
                                if ( v31 == (unsigned __int16)mfc100u_4478(v52, 0) )
                                {
                                  mfc100u_11494(v52, -1);
                                  mfc100u_902(v52);
                                  mfc100u_902(&v51);
                                  mfc100u_902(&v50);
                                  return 1;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_2;
          }
        }
      }
    }
  }
LABEL_2:
  mfc100u_902(v52);
  mfc100u_902(&v51);
  mfc100u_902(&v50);
  return 0;
}
```

So there's some bitwise operation and string comparisons. Z3 maybe?. I also see the limits for the input name and input number on graph view. So the name is of 4 bytes.

Hmm I got the bit manipulations down. I'm missing something to define the solver.

Ok wait so the code defines bitwise manipulation for the 4 variables of the name. Worked a bit with ChatpGpt and yeah it should be z3.

Honestly **itow_s** is doing something here

