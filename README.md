<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dr. Alex Martinelli x Viviane Costa</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#05101d;--n2:#0a1828;--n3:#0f2035;--n4:#162840;
  --gold:#c9a84c;--g2:#e2c97e;--g3:rgba(201,168,76,.13);
  --silver:#8a99ac;--white:#eef2f8;--bd:rgba(201,168,76,.2);
  --green:#4cba85;--red:#e07575;--blue:#5b9fd4;
}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:"Outfit",sans-serif;background:var(--ink);color:var(--white);min-height:100vh}
::-webkit-scrollbar{width:5px}::-webkit-scrollbar-track{background:var(--n2)}::-webkit-scrollbar-thumb{background:var(--gold);border-radius:3px}
.topbar{background:linear-gradient(135deg,#030d19,var(--n2));padding:10px 18px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200;border-bottom:1px solid var(--bd)}
.brand{display:flex;align-items:center;gap:11px}
.brand img{height:44px;width:auto;max-width:160px;object-fit:contain;filter:drop-shadow(0 2px 8px rgba(201,168,76,.3))}
.brand-t{font-family:"Cormorant Garamond",serif;font-size:.95rem;color:var(--white);line-height:1.2}
.brand-t span{font-size:.5rem;letter-spacing:3px;color:var(--gold);text-transform:uppercase;display:block;font-family:"Outfit",sans-serif;margin-top:1px}
.tbr{display:flex;gap:6px}
.bt{padding:7px 14px;border-radius:7px;font-size:.68rem;font-weight:700;cursor:pointer;border:none;letter-spacing:.05em;font-family:"Outfit",sans-serif;transition:all .2s}
#btn-back{background:rgba(255,255,255,.1);color:var(--g2);display:none}
#btn-salvar{background:var(--gold);color:var(--ink);display:none}
.bt:hover{opacity:.85;transform:translateY(-1px)}
#tela-lista{display:block}#tela-ficha{display:none}
.lwrap{max-width:740px;margin:0 auto;padding:24px 14px 80px}
.lhdr{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:20px;flex-wrap:wrap;gap:10px}
.ltit{font-family:"Cormorant Garamond",serif;font-size:1.9rem;color:var(--white);font-weight:400}
.lsub{font-size:.68rem;color:var(--silver);margin-top:3px}
.btn-nova{background:linear-gradient(135deg,var(--gold),#9a6f22);color:var(--ink);padding:10px 20px;border-radius:8px;font-size:.72rem;font-weight:700;cursor:pointer;border:none;letter-spacing:1px;text-transform:uppercase;transition:all .2s}
.btn-nova:hover{opacity:.9;transform:translateY(-1px)}
.si{width:100%;padding:11px 16px;border:1.5px solid var(--bd);border-radius:10px;font-family:"Outfit",sans-serif;font-size:.83rem;background:var(--n3);color:var(--white);margin-bottom:14px;outline:none;transition:border-color .2s}
.si:focus{border-color:var(--gold)}.si::placeholder{color:var(--silver)}
.cc{background:var(--n3);border:1.5px solid var(--bd);border-radius:12px;padding:13px 15px;display:flex;align-items:center;gap:13px;cursor:pointer;margin-bottom:8px;transition:all .2s}
.cc:hover{border-color:var(--gold);transform:translateX(2px)}
.cc-av{width:44px;height:44px;border-radius:50%;background:linear-gradient(135deg,var(--gold),#9a6f22);display:flex;align-items:center;justify-content:center;font-size:.95rem;font-weight:700;color:var(--ink);flex-shrink:0}
.cc-info{flex:1;min-width:0}.cc-nome{font-size:.92rem;color:var(--white);font-weight:600;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.cc-meta{font-size:.65rem;color:var(--silver);margin-top:2px}
.cc-del{background:none;border:none;cursor:pointer;color:var(--silver);font-size:.95rem;padding:4px 8px;border-radius:6px;transition:all .2s;flex-shrink:0}
.cc-del:hover{color:var(--red);background:rgba(224,117,117,.12)}
.cc-arr{font-size:1.1rem;color:var(--bd);flex-shrink:0}
.lvazio{text-align:center;padding:50px 16px;color:var(--silver)}
.tabs{background:var(--n2);display:flex;overflow-x:auto;border-bottom:1px solid var(--bd);position:sticky;top:64px;z-index:99}
.tab{padding:11px 13px;font-size:.62rem;font-weight:700;letter-spacing:.1em;color:var(--silver);background:none;border:none;cursor:pointer;border-bottom:2px solid transparent;white-space:nowrap;font-family:"Outfit",sans-serif;text-transform:uppercase;transition:all .2s}
.tab:hover{color:var(--white)}.tab.on{color:var(--gold);border-bottom-color:var(--gold)}
.main{max-width:960px;margin:0 auto;padding:16px 13px 80px}
.panel{display:none}.panel.on{display:block}
.hero{background:linear-gradient(135deg,var(--n2),var(--n3));border:1px solid var(--bd);border-radius:14px;padding:18px;display:flex;align-items:center;gap:15px;margin-bottom:13px}
.avatar{width:60px;height:60px;border-radius:50%;background:rgba(201,168,76,.13);border:2px solid var(--gold);display:flex;align-items:center;justify-content:center;font-size:1.25rem;color:var(--g2);font-weight:700;flex-shrink:0}
.h-nome{font-family:"Cormorant Garamond",serif;font-size:1.3rem;color:var(--white)}
.h-meta{font-size:.66rem;color:var(--silver);margin-top:3px}
.h-pct{font-family:"Cormorant Garamond",serif;font-size:1.6rem;font-weight:600;color:var(--g2);text-align:center}
.h-pl{font-size:.5rem;color:rgba(201,168,76,.4);letter-spacing:.15em;text-transform:uppercase;text-align:center}
.card{background:var(--n3);border-radius:12px;border:1px solid var(--bd);margin-bottom:11px;overflow:hidden}
.card-h{padding:11px 15px;display:flex;align-items:center;gap:9px;border-bottom:1px solid rgba(201,168,76,.07);cursor:pointer;transition:background .15s}
.card-h:hover{background:rgba(201,168,76,.04)}
.card-ico{width:28px;height:28px;border-radius:6px;background:rgba(201,168,76,.11);display:flex;align-items:center;justify-content:center;font-size:.85rem;flex-shrink:0}
.card-tit{font-size:.9rem;color:var(--white);flex:1;font-weight:500}.card-arr{font-size:.65rem;color:var(--silver)}
.card-b{padding:13px 15px}.card-b.hide{display:none}
.grid{display:grid;gap:9px}.g2{grid-template-columns:1fr 1fr}.g3{grid-template-columns:1fr 1fr 1fr}.g4{grid-template-columns:1fr 1fr 1fr 1fr}
@media(max-width:580px){.g2,.g3,.g4{grid-template-columns:1fr}}@media(max-width:720px){.g4{grid-template-columns:1fr 1fr}}
.full{grid-column:1/-1}
.field{display:flex;flex-direction:column;gap:3px}
.field label{font-size:.55rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;color:var(--silver)}
.fi,.fs,.fta{padding:8px 11px;border:1.5px solid var(--bd);border-radius:7px;font-family:"Outfit",sans-serif;font-size:.8rem;color:var(--white);background:var(--n4);width:100%;outline:none;transition:border-color .2s}
.fi:focus,.fs:focus,.fta:focus{border-color:var(--gold)}.fs option{background:var(--n2)}
.fta{resize:vertical;min-height:68px;line-height:1.5}.fi[readonly]{background:var(--n2);color:var(--silver)}
.togs{display:flex;flex-wrap:wrap;gap:5px;margin-top:4px}
.tog{padding:4px 11px;border-radius:20px;border:1.5px solid var(--bd);font-size:.65rem;font-weight:600;cursor:pointer;background:none;color:var(--silver);transition:all .2s}
.tog:hover{border-color:var(--gold)}.tog.on{background:var(--n4);border-color:var(--gold);color:var(--g2)}
.al{border-radius:8px;padding:9px 12px;display:flex;gap:7px;margin-bottom:7px;font-size:.7rem;line-height:1.5}
.al-err{background:rgba(153,27,27,.15);border:1px solid rgba(153,27,27,.3);color:#fca5a5}
.al-warn{background:rgba(180,83,9,.11);border:1px solid rgba(180,83,9,.25);color:#fcd34d}
.div{height:1px;background:linear-gradient(to right,transparent,var(--bd),transparent);margin:9px 0}
.mtable{width:100%;border-collapse:collapse;font-size:.74rem}
.mtable th{background:rgba(201,168,76,.11);color:var(--g2);padding:7px 9px;text-align:left;font-size:.58rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase}
.mtable td{padding:6px 7px;border-bottom:1px solid rgba(201,168,76,.06);vertical-align:middle}
.mtable input{width:66px;padding:4px 6px;border:1.5px solid var(--bd);border-radius:5px;font-size:.74rem;text-align:center;background:var(--n4);color:var(--white);font-family:"Outfit",sans-serif;outline:none}
.mtable input:focus{border-color:var(--gold)}
.d-ok{color:var(--green);font-weight:700}.d-err{color:var(--red);font-weight:700}.d-n{color:var(--silver)}
.gwrap{background:rgba(201,168,76,.04);border:1px solid var(--bd);border-radius:9px;padding:13px;margin-top:9px}
.gtit{font-size:.56rem;letter-spacing:.15em;text-transform:uppercase;color:var(--silver);font-weight:700;margin-bottom:9px}
.gbars{display:flex;align-items:flex-end;gap:5px;height:88px}
.bw{flex:1;display:flex;flex-direction:column;align-items:center;gap:2px}
.bar{width:100%;background:linear-gradient(to top,var(--gold),var(--g2));border-radius:3px 3px 0 0;min-width:8px}
.bv{font-size:.58rem;font-weight:700;color:var(--g2)}.bl{font-size:.52rem;color:var(--silver);text-align:center}
.trat-section{background:var(--n2);border:1px solid var(--bd);border-radius:12px;margin-bottom:12px;overflow:hidden}
.trat-sh{padding:12px 15px;display:flex;align-items:center;justify-content:space-between;cursor:pointer;transition:background .15s}
.trat-sh:hover{background:rgba(201,168,76,.05)}
.trat-nome{font-size:.88rem;font-weight:600;color:var(--white);display:flex;align-items:center;gap:8px}
.trat-badge{background:rgba(201,168,76,.15);color:var(--g2);border:1px solid var(--bd);font-size:.6rem;font-weight:700;padding:2px 8px;border-radius:10px;letter-spacing:.5px}
.trat-ult{font-size:.62rem;color:var(--silver)}
.trat-body{display:none;padding:0 0 12px}.trat-body.open{display:block}
.sess-item{background:var(--n3);border:1px solid var(--bd);border-radius:9px;margin:8px 12px 0;padding:12px 14px}
.sess-ih{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px}
.sess-nb{background:var(--gold);color:var(--ink);font-size:.68rem;font-weight:700;padding:3px 10px;border-radius:10px}
.sess-dt{font-size:.65rem;color:var(--silver)}
.pgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:7px;margin-top:8px}
.pbox{background:var(--n4);border:1px solid var(--bd);border-radius:7px;padding:8px 10px}
.plbl{font-size:.52rem;letter-spacing:.1em;text-transform:uppercase;color:var(--silver);font-weight:700;margin-bottom:3px}
.pval{font-size:.82rem;font-weight:600;color:var(--g2)}.punit{font-size:.52rem;color:var(--silver);margin-top:1px}
.btn-add-sess{display:flex;align-items:center;gap:6px;background:rgba(201,168,76,.08);border:1px dashed var(--bd);border-radius:8px;padding:8px 14px;cursor:pointer;color:var(--gold);font-size:.7rem;font-weight:600;margin:8px 12px 0;transition:all .2s;font-family:"Outfit",sans-serif;width:calc(100% - 24px)}
.btn-add-sess:hover{background:rgba(201,168,76,.14);border-color:var(--gold)}
.evol-table{width:100%;border-collapse:collapse;font-size:.74rem;margin-bottom:14px}
.evol-table th{background:rgba(201,168,76,.11);color:var(--g2);padding:8px 10px;text-align:left;font-size:.58rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase}
.evol-table td{padding:8px 10px;border-bottom:1px solid rgba(201,168,76,.06);vertical-align:middle}
.kpis{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:9px;margin-bottom:13px}
.kpi{background:var(--n3);border:1px solid var(--bd);border-radius:11px;padding:14px;text-align:center}
.kpi-i{font-size:1.15rem;margin-bottom:3px}
.kpi-v{font-family:"Cormorant Garamond",serif;font-size:1.65rem;font-weight:600;color:var(--g2);line-height:1}
.kpi-u{font-size:.53rem;color:var(--silver);letter-spacing:.1em;margin-top:2px}.kpi-l{font-size:.58rem;color:var(--silver);margin-top:3px}
.stars{display:flex;gap:3px}.star{font-size:1.05rem;cursor:pointer;color:var(--bd);transition:color .15s}.star.on{color:var(--gold)}
.srow{display:flex;align-items:center;gap:9px;padding:8px 0;border-bottom:1px solid rgba(201,168,76,.07)}
.srow:last-child{border:none}.srow-l{flex:1;font-size:.8rem}
.tl{padding-left:19px;position:relative}
.tl::before{content:"";position:absolute;left:6px;top:0;bottom:0;width:1px;background:var(--bd)}
.tli{position:relative;margin-bottom:11px}
.tld{width:13px;height:13px;border-radius:50%;background:var(--gold);border:2px solid var(--n2);position:absolute;left:-19px;top:3px}
.tldt{font-size:.58rem;color:var(--gold);font-weight:600;margin-bottom:2px;letter-spacing:.4px}
.tltx{font-size:.74rem;line-height:1.5;background:var(--n4);border:1px solid var(--bd);border-radius:7px;padding:7px 10px;color:var(--silver)}
.fsum{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:11px;margin-bottom:16px}
.fcard{background:var(--n3);border:1px solid var(--bd);border-radius:11px;padding:15px}
.flbl{font-size:.55rem;letter-spacing:2px;color:var(--silver);text-transform:uppercase;margin-bottom:5px}
.fval{font-family:"Cormorant Garamond",serif;font-size:1.8rem;font-weight:600}
.fcard.rec .fval{color:var(--green)}.fcard.pen .fval{color:var(--g2)}.fcard.tot .fval{color:var(--white)}
.pitem{display:flex;align-items:center;gap:10px;padding:10px 13px;background:var(--n3);border:1px solid var(--bd);border-radius:9px;margin-bottom:7px}
.pitem:hover{border-color:var(--gold)}
.pico{font-size:1.05rem;flex-shrink:0}.pinfo{flex:1}
.pnm{font-size:.76rem;font-weight:600;color:var(--white)}.ppr{font-size:.62rem;color:var(--silver)}
.pv{font-size:.86rem;font-weight:700}.pv.pago{color:var(--green)}.pv.pend{color:var(--g2)}
.spill{font-size:.55rem;font-weight:700;padding:2px 7px;border-radius:9px;letter-spacing:1px;text-transform:uppercase}
.sp-pago{background:rgba(76,186,133,.13);color:var(--green);border:1px solid rgba(76,186,133,.28)}
.sp-pend{background:rgba(201,168,76,.13);color:var(--gold);border:1px solid rgba(201,168,76,.28)}
.sp-parc{background:rgba(91,159,212,.13);color:var(--blue);border:1px solid rgba(91,159,212,.28)}
.rx-preview{background:white;color:#1a1a1a;border-radius:10px;padding:28px;font-family:"Outfit",sans-serif}
.rx-h{text-align:center;border-bottom:2px solid #c9a84c;padding-bottom:16px;margin-bottom:18px}
.rx-brand{font-family:"Cormorant Garamond",serif;font-size:1.65rem;color:#06101e}
.rx-sub{font-size:.6rem;letter-spacing:3px;color:#c9a84c;text-transform:uppercase}
.rx-crm{font-size:.68rem;color:#666;margin-top:2px}.rx-end{font-size:.66rem;color:#888;margin-top:2px}
.rx-pac{display:grid;grid-template-columns:1fr 1fr;gap:7px;margin-bottom:16px;font-size:.74rem;color:#555;background:#f9f6f0;padding:10px;border-radius:7px}
.rx-body{border:1px solid #ddd;border-radius:8px;padding:14px;margin-bottom:14px}
.rx-sym{font-size:2rem;color:#c9a84c;font-family:"Cormorant Garamond",serif;margin-bottom:8px}
.rx-item{margin-bottom:12px;padding-bottom:12px;border-bottom:1px solid #f0f0f0}
.rx-item:last-child{border:none;margin:0;padding:0}
.rx-med{font-weight:700;font-size:.84rem;color:#1a1a1a}.rx-dose{font-size:.74rem;color:#555;margin-top:2px}
.rx-ass{text-align:center;margin-top:20px;padding-top:16px;border-top:1px solid #ddd}
.rx-ass-line{display:inline-block;border-top:1px solid #aaa;width:220px;padding-top:8px;font-size:.72rem;color:#555}
.rx-foot{text-align:center;font-size:.6rem;color:#aaa;margin-top:12px}
.prot-cats{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:16px}
.pcat{padding:5px 15px;border-radius:20px;border:1.5px solid var(--bd);font-size:.67rem;font-weight:600;cursor:pointer;background:none;color:var(--silver);transition:all .2s;font-family:"Outfit",sans-serif}
.pcat:hover,.pcat.on{background:var(--n4);border-color:var(--gold);color:var(--g2)}
.pgrid2{display:grid;grid-template-columns:repeat(auto-fill,minmax(290px,1fr));gap:14px}
.pcard{border-radius:13px;overflow:hidden;border:1.5px solid var(--bd);transition:all .25s;cursor:pointer}
.pcard:hover{transform:translateY(-3px);border-color:var(--gold)}
.pbadge{padding:13px 15px;display:flex;align-items:center;justify-content:space-between}
.pname{font-family:"Cormorant Garamond",serif;font-size:1.1rem;font-weight:600;line-height:1.2}
.psub{font-size:.58rem;letter-spacing:.1em;text-transform:uppercase;opacity:.6;margin-top:2px}
.picon{font-size:1.7rem}
.pbody{padding:13px 15px;background:var(--n3);border-top:1px solid rgba(255,255,255,.05)}
.pstep{display:flex;align-items:flex-start;gap:9px;padding:6px 0;border-bottom:1px solid rgba(201,168,76,.06);font-size:.72rem}
.pstep:last-child{border:none}
.psn{width:20px;height:20px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:.58rem;font-weight:700;flex-shrink:0}
.pstxt{flex:1;line-height:1.4;color:var(--silver)}
.pstxt strong{color:var(--white);display:block;margin-bottom:1px}
.pdet{display:none;padding:13px 15px;background:var(--n2);border-top:1px solid var(--bd)}
.pdet.open{display:block}
.ppr2{display:flex;justify-content:space-between;padding:5px 0;font-size:.7rem;border-bottom:1px solid rgba(201,168,76,.06)}
.ppr2:last-child{border:none}.ppk{color:var(--silver)}.ppv{color:var(--g2);font-weight:600}
.tpick-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(110px,1fr));gap:7px;margin-bottom:14px}
.tpick{background:var(--n4);border:1.5px solid var(--bd);border-radius:10px;padding:10px 8px;cursor:pointer;text-align:center;transition:all .2s}
.tpick:hover{border-color:var(--gold)}.tpick.on{border-color:var(--gold);background:rgba(201,168,76,.1)}
.tpick-ico{font-size:1.6rem;margin-bottom:5px}
.tpick-lbl{font-size:.62rem;font-weight:600;color:var(--silver);line-height:1.3}
.tpick-who{font-size:.55rem;font-weight:700;padding:2px 6px;border-radius:8px;margin-top:4px;display:inline-block}
.who-alex{background:rgba(96,165,250,.13);color:#93c5fd}
.who-vivi{background:rgba(201,168,76,.13);color:var(--gold)}
.sec-lbl{font-size:.55rem;letter-spacing:2px;text-transform:uppercase;font-weight:700;padding:8px 0 5px;grid-column:1/-1;border-bottom:1px solid var(--bd);margin-bottom:2px}
.sec-alex{color:#60a5fa}.sec-vivi{color:var(--gold)}
.ov{display:none;position:fixed;inset:0;background:rgba(0,0,0,.8);z-index:500;align-items:center;justify-content:center;backdrop-filter:blur(5px)}
.ov.open{display:flex;animation:fi .2s}
@keyframes fi{from{opacity:0}to{opacity:1}}
.modal{background:linear-gradient(135deg,var(--n2),var(--n3));border:1px solid var(--bd);border-radius:15px;padding:24px;width:560px;max-width:95vw;max-height:90vh;overflow-y:auto;box-shadow:0 12px 40px rgba(0,0,0,.5);animation:su .22s}
@keyframes su{from{transform:translateY(20px);opacity:0}to{transform:none;opacity:1}}
.mhdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}
.mtit{font-family:"Cormorant Garamond",serif;font-size:1.25rem;color:var(--white)}
.mclose{background:none;border:1px solid var(--bd);color:var(--silver);width:27px;height:27px;border-radius:6px;cursor:pointer;font-size:.85rem;transition:all .2s;display:flex;align-items:center;justify-content:center}
.mclose:hover{border-color:var(--gold);color:var(--gold)}
.mact{display:flex;gap:8px;margin-top:16px}
.sdiv{font-size:.55rem;letter-spacing:3px;color:var(--gold);text-transform:uppercase;margin:14px 0 9px;padding-bottom:6px;border-bottom:1px solid var(--bd)}
.btn{padding:8px 15px;border-radius:7px;font-size:.68rem;font-weight:700;cursor:pointer;border:none;display:inline-flex;align-items:center;gap:5px;font-family:"Outfit",sans-serif;letter-spacing:.5px;text-transform:uppercase;transition:all .2s}
.btn-g{background:linear-gradient(135deg,var(--gold),#9a6f22);color:var(--ink)}.btn-g:hover{opacity:.9;transform:translateY(-1px)}
.btn-m{background:var(--n4);color:var(--g2);border:1px solid var(--bd)}.btn-m:hover{border-color:var(--gold)}
.toast{position:fixed;bottom:22px;left:50%;transform:translateX(-50%) translateY(80px);background:var(--green);color:white;padding:11px 22px;border-radius:22px;font-size:.75rem;font-weight:700;z-index:600;transition:transform .32s cubic-bezier(.34,1.56,.64,1);white-space:nowrap}
.toast.show{transform:translateX(-50%) translateY(0)}.toast.err{background:var(--red)}
input[type=file]{display:none}

.ia-wrap{background:linear-gradient(135deg,rgba(201,168,76,.06),rgba(45,212,191,.04));border:1.5px solid rgba(201,168,76,.25);border-radius:14px;padding:20px;margin-bottom:16px;position:relative;overflow:hidden}
.ia-wrap::before{content:"";position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,transparent,#c9a84c,#2dd4bf,transparent)}
.ia-header{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.ia-icon{width:36px;height:36px;border-radius:10px;background:linear-gradient(135deg,#c9a84c,#9a6f22);display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0;color:#060d18}
.ia-title{font-family:"Cormorant Garamond",serif;font-size:1.1rem;color:#eef2f8}
.ia-sub{font-size:.6rem;color:#8a99ac;margin-top:1px}
.ia-btn{background:linear-gradient(135deg,#c9a84c,#9a6f22);color:#060d18;border:none;padding:9px 20px;border-radius:8px;font-size:.72rem;font-weight:700;cursor:pointer;letter-spacing:1px;text-transform:uppercase;font-family:"Outfit",sans-serif;transition:all .2s}
.ia-btn:hover{opacity:.9;transform:translateY(-1px)}.ia-btn:disabled{opacity:.5;cursor:not-allowed;transform:none}
.ia-loading{display:flex;align-items:center;gap:8px;color:#8a99ac;font-size:.78rem;padding:12px 0}
.ia-dot{width:6px;height:6px;border-radius:50%;background:#c9a84c;animation:iap .8s ease-in-out infinite}
.ia-dot:nth-child(2){animation-delay:.15s}.ia-dot:nth-child(3){animation-delay:.3s}
@keyframes iap{0%,100%{opacity:.3;transform:scale(1)}50%{opacity:1;transform:scale(1.3)}}
.ia-result{display:none}.ia-result.show{display:block}
.ia-prot-card{border-radius:11px;padding:16px;margin-bottom:10px;border:1.5px solid rgba(201,168,76,.2)}
.ia-prot-rank{font-size:.5rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;margin-bottom:6px}
.ia-prot-name{font-family:"Cormorant Garamond",serif;font-size:1.2rem;font-weight:600;margin-bottom:5px}
.ia-prot-why{font-size:.74rem;color:#8a99ac;line-height:1.6;margin-bottom:10px}
.ia-prot-match{display:flex;align-items:center;gap:8px;margin-bottom:8px}
.ia-match-bar{flex:1;height:6px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden}
.ia-match-fill{height:100%;border-radius:3px;transition:width 1s ease}
.ia-match-pct{font-size:.65rem;font-weight:700;color:#e2c97e;min-width:32px}
.ia-steps{display:flex;flex-wrap:wrap;gap:5px;margin-top:8px}
.ia-step{font-size:.6rem;padding:3px 9px;border-radius:10px;font-weight:600}
.ia-warn{background:rgba(224,117,117,.1);border:1px solid rgba(224,117,117,.25);border-radius:9px;padding:10px 13px;font-size:.74rem;color:#fca5a5;line-height:1.5;margin-bottom:8px;display:flex;gap:8px}
.ia-next{background:rgba(76,186,133,.08);border:1px solid rgba(76,186,133,.2);border-radius:9px;padding:12px 14px;font-size:.76rem;color:#eef2f8;line-height:1.6;margin-top:8px}
.ia-next strong{color:#4cba85}

/* ══ LOGIN ══ */
#tela-login{display:none;position:fixed;inset:0;background:linear-gradient(145deg,#030912,#07121e,#030912);z-index:1000;align-items:center;justify-content:center}
#tela-login.show{display:flex}
.login-card{background:linear-gradient(145deg,#080f1c,#0d1828);border:1.5px solid rgba(201,168,76,.2);border-radius:20px;padding:44px 36px;width:380px;max-width:94vw;position:relative;overflow:hidden;box-shadow:0 30px 80px rgba(0,0,0,.7)}
.login-card::before{content:"";position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,transparent,#c9a84c,transparent)}
.login-logo{text-align:center;margin-bottom:32px}
.login-brand{font-family:"Cormorant Garamond",serif;font-size:2rem;font-weight:600;color:#e8c97a;letter-spacing:1px}
.login-tag{font-size:.5rem;letter-spacing:4px;color:#c9a84c;text-transform:uppercase;margin-top:4px}
.login-field{margin-bottom:14px}
.login-field label{font-size:.55rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:#8a99ac;display:block;margin-bottom:5px}
.login-field input{width:100%;padding:11px 14px;border:1.5px solid rgba(201,168,76,.2);border-radius:9px;background:#060d18;color:#eef2f8;font-family:"Outfit",sans-serif;font-size:.88rem;outline:none;transition:border-color .2s}
.login-field input:focus{border-color:#c9a84c}
.login-field input::placeholder{color:#3a4a5a}
.login-btn{width:100%;padding:13px;background:linear-gradient(135deg,#c9a84c,#9a6f22);color:#060d18;border:none;border-radius:9px;font-family:"Outfit",sans-serif;font-size:.82rem;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;cursor:pointer;transition:all .2s;margin-top:6px}
.login-btn:hover{opacity:.9;transform:translateY(-1px)}
.login-btn:disabled{opacity:.5;cursor:not-allowed;transform:none}
.login-err{background:rgba(224,117,117,.12);border:1px solid rgba(224,117,117,.3);border-radius:8px;padding:9px 13px;font-size:.75rem;color:#fca5a5;margin-bottom:12px;display:none}
.login-err.show{display:block}
.login-divider{display:flex;align-items:center;gap:10px;margin:18px 0}
.login-divider::before,.login-divider::after{content:"";flex:1;height:1px;background:rgba(201,168,76,.15)}
.login-divider span{font-size:.58rem;color:#3a4a5a;letter-spacing:1px}
.login-footer{text-align:center;font-size:.62rem;color:#2a3a4a;margin-top:18px}
.login-link{color:#c9a84c;cursor:pointer;text-decoration:underline}
.login-orb{position:absolute;border-radius:50%;filter:blur(60px);pointer-events:none}
.lo1{width:200px;height:200px;background:rgba(201,168,76,.05);top:-60px;right:-60px}
.lo2{width:150px;height:150px;background:rgba(45,212,191,.04);bottom:-40px;left:-40px}
/* Logout btn */
.logout-btn{background:none;border:1px solid rgba(201,168,76,.2);color:#8a99ac;padding:5px 12px;border-radius:6px;font-size:.6rem;cursor:pointer;font-family:"Outfit",sans-serif;transition:all .2s}
.logout-btn:hover{border-color:#c9a84c;color:#c9a84c}

/* ══ AGENDA ══ */
.ag-week{display:grid;grid-template-columns:60px repeat(7,1fr);border:1px solid var(--bd);border-radius:12px;overflow:hidden;background:var(--n2)}
.ag-head{background:var(--n3);border-bottom:1px solid var(--bd)}
.ag-head-cell{padding:9px 6px;text-align:center;border-right:1px solid var(--bd);cursor:pointer;transition:background .15s}
.ag-head-cell:hover{background:rgba(201,168,76,.07)}
.ag-head-cell.hoje{background:rgba(201,168,76,.12)}
.ag-head-cell.hoje .ag-day-num{background:var(--gold);color:var(--ink);border-radius:50%;width:26px;height:26px;display:flex;align-items:center;justify-content:center;margin:0 auto}
.ag-day-nome{font-size:.55rem;color:var(--silver);text-transform:uppercase;letter-spacing:1px}
.ag-day-num{font-size:.95rem;font-weight:700;color:var(--white);margin-top:2px}
.ag-time-col{background:var(--n3);border-right:1px solid var(--bd)}
.ag-time-cell{height:48px;display:flex;align-items:flex-start;justify-content:flex-end;padding:3px 8px 0 0;font-size:.58rem;color:rgba(138,153,172,.5);border-bottom:1px solid rgba(201,168,76,.04)}
.ag-day-col{border-right:1px solid rgba(201,168,76,.06);position:relative;cursor:pointer;transition:background .1s}
.ag-day-col:last-child{border-right:none}
.ag-day-col:hover{background:rgba(201,168,76,.03)}
.ag-slot{height:48px;border-bottom:1px solid rgba(201,168,76,.04)}
.ag-event{position:absolute;left:2px;right:2px;border-radius:6px;padding:3px 6px;font-size:.62rem;cursor:pointer;overflow:hidden;transition:all .2s;z-index:2;border-left:3px solid transparent}
.ag-event:hover{filter:brightness(1.15);z-index:3}
.ag-event-pac{font-weight:700;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--ink)}
.ag-event-proc{font-size:.55rem;opacity:.85;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--ink)}
.ag-event-hora{font-size:.52rem;opacity:.7;color:var(--ink)}
.ag-status-agendado{background:rgba(91,159,212,.25);border-left-color:#5b9fd4}
.ag-status-confirmado{background:rgba(76,186,133,.25);border-left-color:#4cba85}
.ag-status-realizado{background:rgba(201,168,76,.25);border-left-color:#c9a84c}
.ag-status-cancelado{background:rgba(224,117,117,.2);border-left-color:#e07575;opacity:.6}
.ag-status-faltou{background:rgba(180,83,9,.2);border-left-color:#f97316;opacity:.6}
.ag-item{background:var(--n3);border:1px solid var(--bd);border-radius:10px;padding:12px 14px;margin-bottom:8px;display:flex;align-items:center;gap:12px;transition:all .2s;cursor:pointer}
.ag-item:hover{border-color:var(--gold);transform:translateX(2px)}
.ag-item-hora{font-family:"Cormorant Garamond",serif;font-size:1.1rem;font-weight:600;color:var(--g2);min-width:48px;text-align:center}
.ag-item-dur{font-size:.55rem;color:var(--silver);text-align:center}
.ag-item-info{flex:1}
.ag-item-pac{font-size:.88rem;font-weight:600;color:var(--white)}
.ag-item-proc{font-size:.68rem;color:var(--silver);margin-top:2px}
.ag-item-prof{font-size:.6rem;padding:2px 8px;border-radius:8px;font-weight:700;display:inline-block;margin-top:4px}
.ag-prof-alex{background:rgba(96,165,250,.13);color:#93c5fd}
.ag-prof-vivi{background:rgba(201,168,76,.13);color:var(--gold)}
.ag-prof-ambos{background:rgba(159,110,199,.13);color:#c4b5fd}
.ag-pill{font-size:.55rem;font-weight:700;padding:2px 8px;border-radius:8px;letter-spacing:.5px;text-transform:uppercase}
.ag-pill-agendado{background:rgba(91,159,212,.15);color:#5b9fd4}
.ag-pill-confirmado{background:rgba(76,186,133,.15);color:#4cba85}
.ag-pill-realizado{background:rgba(201,168,76,.15);color:var(--gold)}
.ag-pill-cancelado{background:rgba(224,117,117,.15);color:#e07575}
.ag-pill-faltou{background:rgba(249,115,22,.15);color:#f97316}
@media print{.topbar,.tabs,.btn,.btn-nova,.bt{display:none!important}}

/* RELATÓRIO PDF */
.rel-preview{background:white;color:#1a1a1a;font-family:"Outfit",sans-serif;padding:0;border-radius:10px;overflow:hidden}
.rel-capa{background:linear-gradient(135deg,#060d18,#0e1e30);padding:32px 28px;text-align:center;position:relative}
.rel-capa::after{content:"";position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(to right,transparent,#c9a84c,transparent)}
.rel-marca{font-family:"Cormorant Garamond",serif;font-size:1.8rem;color:#e8c97a;font-weight:600;margin-bottom:2px}
.rel-subtit{font-size:.55rem;letter-spacing:3px;color:#c9a84c;text-transform:uppercase}
.rel-pac-nome{font-size:1.3rem;font-weight:700;color:white;margin-top:16px}
.rel-periodo{font-size:.7rem;color:rgba(255,255,255,.5);margin-top:4px}
.rel-body{padding:24px 28px}
.rel-section{margin-bottom:22px}
.rel-section-title{font-size:.55rem;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:#8a6f2e;border-bottom:1.5px solid #c9a84c;padding-bottom:6px;margin-bottom:14px}
.rel-kpis{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:14px}
.rel-kpi{background:#f8f6f0;border-radius:8px;padding:12px 8px;text-align:center;border:1px solid rgba(201,168,76,.2)}
.rel-kv{font-family:"Cormorant Garamond",serif;font-size:1.6rem;font-weight:700;color:#8a6f2e;line-height:1}
.rel-kl{font-size:.52rem;color:#888;margin-top:3px}
.rel-med-row{display:flex;align-items:center;gap:10px;padding:7px 0;border-bottom:1px solid #f0ece0;font-size:.75rem}
.rel-med-reg{width:100px;color:#555;flex-shrink:0}
.rel-med-ini{width:44px;text-align:center;color:#888;font-size:.7rem}
.rel-med-bar-wrap{flex:1;height:7px;background:#f0ece0;border-radius:4px;overflow:hidden}
.rel-med-bar{height:100%;background:linear-gradient(to right,#c9a84c,#e8c97a);border-radius:4px}
.rel-med-ult{width:44px;text-align:center;color:#1a1a1a;font-weight:700;font-size:.72rem}
.rel-med-delta{width:44px;text-align:right;font-weight:700;font-size:.72rem}
.rel-med-delta.pos{color:#4cba85}.rel-med-delta.neg{color:#e07575}.rel-med-delta.neu{color:#888}
.rel-sess-row{display:flex;align-items:center;gap:8px;padding:6px 10px;background:#f9f7f2;border-radius:7px;margin-bottom:5px;font-size:.72rem}
.rel-sess-ico{width:26px;height:26px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:.65rem;font-weight:700;color:white;flex-shrink:0}
.rel-sess-nome{flex:1;font-weight:600;color:#1a1a1a}
.rel-sess-qt{font-size:.65rem;color:#888}
.rel-stars{color:#c9a84c;font-size:.85rem}
.rel-stars-row{display:flex;align-items:center;justify-content:space-between;padding:7px 0;border-bottom:1px solid #f0ece0;font-size:.75rem}
.rel-stars-lbl{color:#555}
.rel-footer{background:#f8f6f0;padding:16px 28px;text-align:center;border-top:2px solid #c9a84c}
.rel-footer-brand{font-family:"Cormorant Garamond",serif;font-size:.95rem;color:#8a6f2e;font-weight:600}
.rel-footer-tag{font-size:.5rem;letter-spacing:2px;color:#b8a888;text-transform:uppercase;margin-top:2px}
/* COMPARATIVO PARÂMETROS */
.comp-wrap{overflow-x:auto}
.comp-table{width:100%;border-collapse:collapse;font-size:.72rem}
.comp-table th{background:var(--n3);color:var(--g2);padding:8px 10px;text-align:left;font-size:.58rem;letter-spacing:.1em;text-transform:uppercase;border-bottom:2px solid var(--bd)}
.comp-table td{padding:7px 10px;border-bottom:1px solid rgba(201,168,76,.06);vertical-align:top}
.comp-table tr:hover td{background:rgba(201,168,76,.03)}
.comp-param{color:var(--silver);font-size:.65rem}
.comp-val{font-weight:600;color:var(--white)}
.comp-val.changed{color:var(--gold)}
.comp-badge{background:rgba(201,168,76,.12);color:var(--g2);font-size:.55rem;font-weight:700;padding:2px 7px;border-radius:8px}
/* PORTAL DO PACIENTE */
.portal-wrap{background:linear-gradient(135deg,#030912,#07121e);border:1.5px solid rgba(201,168,76,.2);border-radius:14px;padding:24px;margin-bottom:14px}
.portal-qr{width:80px;height:80px;background:white;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:.6rem;color:#333;text-align:center;padding:8px;flex-shrink:0}
.portal-link{font-size:.7rem;color:var(--gold);word-break:break-all;font-family:monospace;background:rgba(201,168,76,.08);padding:8px 12px;border-radius:7px;border:1px solid var(--bd)}
/* SCORE PROTOCOLO */
.score-wrap{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:14px}
.score-card{background:var(--n3);border:1px solid var(--bd);border-radius:12px;padding:16px;transition:all .2s}
.score-card:hover{border-color:var(--gold);transform:translateY(-2px)}
.score-name{font-family:"Cormorant Garamond",serif;font-size:1.1rem;color:var(--white);margin-bottom:10px}
.score-bar-row{display:flex;align-items:center;gap:8px;margin-bottom:5px}
.score-bar-lbl{font-size:.6rem;color:var(--silver);width:80px;flex-shrink:0}
.score-bar-bg{flex:1;height:5px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden}
.score-bar-fill{height:100%;border-radius:3px;background:linear-gradient(to right,var(--gold),var(--g2))}
.score-val{font-size:.62rem;font-weight:700;color:var(--g2);width:28px;text-align:right}
.score-n{font-size:.6rem;color:var(--silver);margin-top:6px}

.ia-wrap{background:linear-gradient(135deg,rgba(201,168,76,.06),rgba(45,212,191,.04));border:1.5px solid rgba(201,168,76,.25);border-radius:14px;padding:20px;margin-bottom:16px;position:relative;overflow:hidden}
.ia-wrap::before{content:"";position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,transparent,#c9a84c,#2dd4bf,transparent)}
.ia-header{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.ia-icon{width:36px;height:36px;border-radius:10px;background:linear-gradient(135deg,#c9a84c,#9a6f22);display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0;color:#060d18}
.ia-title{font-family:"Cormorant Garamond",serif;font-size:1.1rem;color:#eef2f8}
.ia-sub{font-size:.6rem;color:#8a99ac;margin-top:1px}
.ia-btn{background:linear-gradient(135deg,#c9a84c,#9a6f22);color:#060d18;border:none;padding:9px 20px;border-radius:8px;font-size:.72rem;font-weight:700;cursor:pointer;letter-spacing:1px;text-transform:uppercase;font-family:"Outfit",sans-serif;transition:all .2s}
.ia-btn:hover{opacity:.9;transform:translateY(-1px)}.ia-btn:disabled{opacity:.5;cursor:not-allowed;transform:none}
.ia-loading{display:flex;align-items:center;gap:8px;color:#8a99ac;font-size:.78rem;padding:12px 0}
.ia-dot{width:6px;height:6px;border-radius:50%;background:#c9a84c;animation:iap .8s ease-in-out infinite}
.ia-dot:nth-child(2){animation-delay:.15s}.ia-dot:nth-child(3){animation-delay:.3s}
@keyframes iap{0%,100%{opacity:.3;transform:scale(1)}50%{opacity:1;transform:scale(1.3)}}
.ia-result{display:none}.ia-result.show{display:block}
.ia-prot-card{border-radius:11px;padding:16px;margin-bottom:10px;border:1.5px solid rgba(201,168,76,.2)}
.ia-prot-rank{font-size:.5rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;margin-bottom:6px}
.ia-prot-name{font-family:"Cormorant Garamond",serif;font-size:1.2rem;font-weight:600;margin-bottom:5px}
.ia-prot-why{font-size:.74rem;color:#8a99ac;line-height:1.6;margin-bottom:10px}
.ia-prot-match{display:flex;align-items:center;gap:8px;margin-bottom:8px}
.ia-match-bar{flex:1;height:6px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden}
.ia-match-fill{height:100%;border-radius:3px;transition:width 1s ease}
.ia-match-pct{font-size:.65rem;font-weight:700;color:#e2c97e;min-width:32px}
.ia-steps{display:flex;flex-wrap:wrap;gap:5px;margin-top:8px}
.ia-step{font-size:.6rem;padding:3px 9px;border-radius:10px;font-weight:600}
.ia-warn{background:rgba(224,117,117,.1);border:1px solid rgba(224,117,117,.25);border-radius:9px;padding:10px 13px;font-size:.74rem;color:#fca5a5;line-height:1.5;margin-bottom:8px;display:flex;gap:8px}
.ia-next{background:rgba(76,186,133,.08);border:1px solid rgba(76,186,133,.2);border-radius:9px;padding:12px 14px;font-size:.76rem;color:#eef2f8;line-height:1.6;margin-top:8px}
.ia-next strong{color:#4cba85}

/* ══ LOGIN ══ */
#tela-login{display:none;position:fixed;inset:0;background:linear-gradient(145deg,#030912,#07121e,#030912);z-index:1000;align-items:center;justify-content:center}
#tela-login.show{display:flex}
.login-card{background:linear-gradient(145deg,#080f1c,#0d1828);border:1.5px solid rgba(201,168,76,.2);border-radius:20px;padding:44px 36px;width:380px;max-width:94vw;position:relative;overflow:hidden;box-shadow:0 30px 80px rgba(0,0,0,.7)}
.login-card::before{content:"";position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,transparent,#c9a84c,transparent)}
.login-logo{text-align:center;margin-bottom:32px}
.login-brand{font-family:"Cormorant Garamond",serif;font-size:2rem;font-weight:600;color:#e8c97a;letter-spacing:1px}
.login-tag{font-size:.5rem;letter-spacing:4px;color:#c9a84c;text-transform:uppercase;margin-top:4px}
.login-field{margin-bottom:14px}
.login-field label{font-size:.55rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:#8a99ac;display:block;margin-bottom:5px}
.login-field input{width:100%;padding:11px 14px;border:1.5px solid rgba(201,168,76,.2);border-radius:9px;background:#060d18;color:#eef2f8;font-family:"Outfit",sans-serif;font-size:.88rem;outline:none;transition:border-color .2s}
.login-field input:focus{border-color:#c9a84c}
.login-field input::placeholder{color:#3a4a5a}
.login-btn{width:100%;padding:13px;background:linear-gradient(135deg,#c9a84c,#9a6f22);color:#060d18;border:none;border-radius:9px;font-family:"Outfit",sans-serif;font-size:.82rem;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;cursor:pointer;transition:all .2s;margin-top:6px}
.login-btn:hover{opacity:.9;transform:translateY(-1px)}
.login-btn:disabled{opacity:.5;cursor:not-allowed;transform:none}
.login-err{background:rgba(224,117,117,.12);border:1px solid rgba(224,117,117,.3);border-radius:8px;padding:9px 13px;font-size:.75rem;color:#fca5a5;margin-bottom:12px;display:none}
.login-err.show{display:block}
.login-divider{display:flex;align-items:center;gap:10px;margin:18px 0}
.login-divider::before,.login-divider::after{content:"";flex:1;height:1px;background:rgba(201,168,76,.15)}
.login-divider span{font-size:.58rem;color:#3a4a5a;letter-spacing:1px}
.login-footer{text-align:center;font-size:.62rem;color:#2a3a4a;margin-top:18px}
.login-link{color:#c9a84c;cursor:pointer;text-decoration:underline}
.login-orb{position:absolute;border-radius:50%;filter:blur(60px);pointer-events:none}
.lo1{width:200px;height:200px;background:rgba(201,168,76,.05);top:-60px;right:-60px}
.lo2{width:150px;height:150px;background:rgba(45,212,191,.04);bottom:-40px;left:-40px}
/* Logout btn */
.logout-btn{background:none;border:1px solid rgba(201,168,76,.2);color:#8a99ac;padding:5px 12px;border-radius:6px;font-size:.6rem;cursor:pointer;font-family:"Outfit",sans-serif;transition:all .2s}
.logout-btn:hover{border-color:#c9a84c;color:#c9a84c}

/* ══ AGENDA ══ */
.ag-week{display:grid;grid-template-columns:60px repeat(7,1fr);border:1px solid var(--bd);border-radius:12px;overflow:hidden;background:var(--n2)}
.ag-head{background:var(--n3);border-bottom:1px solid var(--bd)}
.ag-head-cell{padding:9px 6px;text-align:center;border-right:1px solid var(--bd);cursor:pointer;transition:background .15s}
.ag-head-cell:hover{background:rgba(201,168,76,.07)}
.ag-head-cell.hoje{background:rgba(201,168,76,.12)}
.ag-head-cell.hoje .ag-day-num{background:var(--gold);color:var(--ink);border-radius:50%;width:26px;height:26px;display:flex;align-items:center;justify-content:center;margin:0 auto}
.ag-day-nome{font-size:.55rem;color:var(--silver);text-transform:uppercase;letter-spacing:1px}
.ag-day-num{font-size:.95rem;font-weight:700;color:var(--white);margin-top:2px}
.ag-time-col{background:var(--n3);border-right:1px solid var(--bd)}
.ag-time-cell{height:48px;display:flex;align-items:flex-start;justify-content:flex-end;padding:3px 8px 0 0;font-size:.58rem;color:rgba(138,153,172,.5);border-bottom:1px solid rgba(201,168,76,.04)}
.ag-day-col{border-right:1px solid rgba(201,168,76,.06);position:relative;cursor:pointer;transition:background .1s}
.ag-day-col:last-child{border-right:none}
.ag-day-col:hover{background:rgba(201,168,76,.03)}
.ag-slot{height:48px;border-bottom:1px solid rgba(201,168,76,.04)}
.ag-event{position:absolute;left:2px;right:2px;border-radius:6px;padding:3px 6px;font-size:.62rem;cursor:pointer;overflow:hidden;transition:all .2s;z-index:2;border-left:3px solid transparent}
.ag-event:hover{filter:brightness(1.15);z-index:3}
.ag-event-pac{font-weight:700;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--ink)}
.ag-event-proc{font-size:.55rem;opacity:.85;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;color:var(--ink)}
.ag-event-hora{font-size:.52rem;opacity:.7;color:var(--ink)}
.ag-status-agendado{background:rgba(91,159,212,.25);border-left-color:#5b9fd4}
.ag-status-confirmado{background:rgba(76,186,133,.25);border-left-color:#4cba85}
.ag-status-realizado{background:rgba(201,168,76,.25);border-left-color:#c9a84c}
.ag-status-cancelado{background:rgba(224,117,117,.2);border-left-color:#e07575;opacity:.6}
.ag-status-faltou{background:rgba(180,83,9,.2);border-left-color:#f97316;opacity:.6}
.ag-item{background:var(--n3);border:1px solid var(--bd);border-radius:10px;padding:12px 14px;margin-bottom:8px;display:flex;align-items:center;gap:12px;transition:all .2s;cursor:pointer}
.ag-item:hover{border-color:var(--gold);transform:translateX(2px)}
.ag-item-hora{font-family:"Cormorant Garamond",serif;font-size:1.1rem;font-weight:600;color:var(--g2);min-width:48px;text-align:center}
.ag-item-dur{font-size:.55rem;color:var(--silver);text-align:center}
.ag-item-info{flex:1}
.ag-item-pac{font-size:.88rem;font-weight:600;color:var(--white)}
.ag-item-proc{font-size:.68rem;color:var(--silver);margin-top:2px}
.ag-item-prof{font-size:.6rem;padding:2px 8px;border-radius:8px;font-weight:700;display:inline-block;margin-top:4px}
.ag-prof-alex{background:rgba(96,165,250,.13);color:#93c5fd}
.ag-prof-vivi{background:rgba(201,168,76,.13);color:var(--gold)}
.ag-prof-ambos{background:rgba(159,110,199,.13);color:#c4b5fd}
.ag-pill{font-size:.55rem;font-weight:700;padding:2px 8px;border-radius:8px;letter-spacing:.5px;text-transform:uppercase}
.ag-pill-agendado{background:rgba(91,159,212,.15);color:#5b9fd4}
.ag-pill-confirmado{background:rgba(76,186,133,.15);color:#4cba85}
.ag-pill-realizado{background:rgba(201,168,76,.15);color:var(--gold)}
.ag-pill-cancelado{background:rgba(224,117,117,.15);color:#e07575}
.ag-pill-faltou{background:rgba(249,115,22,.15);color:#f97316}
@media print{.topbar,.tabs,.btn,.btn-nova,.bt,.mact,button{display:none!important}.ov{position:static!important;background:none!important;backdrop-filter:none!important}.modal{box-shadow:none!important;border:none!important;max-height:none!important;width:100%!important}}
</style>
</head>
<body>
<!-- TELA DE LOGIN -->
<div id="tela-login">
  <div class="login-card">
    <div class="login-orb lo1"></div>
    <div class="login-orb lo2"></div>
    <div class="login-logo">
      <div class="login-brand">Intelectus</div>
      <div class="login-tag">Gestão Inteligente</div>
    </div>
    <div class="login-err" id="login-err"></div>
    <div id="login-form">
      <div class="login-field">
        <label>E-mail</label>
        <input type="email" id="login-email" placeholder="seu@email.com" autocomplete="email">
      </div>
      <div class="login-field">
        <label>Senha</label>
        <input type="password" id="login-senha" placeholder="••••••••" autocomplete="current-password">
      </div>
      <button class="login-btn" id="login-btn" onclick="fazerLogin()">Entrar</button>
      <div class="login-divider"><span>ou</span></div>
      <button class="login-btn" style="background:linear-gradient(135deg,#162440,#0e1828);color:#e8c97a;border:1.5px solid rgba(201,168,76,.3)" onclick="loginGoogle()">Entrar com Google</button>
    </div>
    <div class="login-footer">
      Esqueceu a senha? <span class="login-link" onclick="resetSenha()">Recuperar acesso</span>
    </div>
  </div>
</div>

<div class="topbar">
  <div class="brand">
    <img id="logo-img" src="data:image/jpeg;base64,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AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAf/8QAAv/aAAwDAQACAAMAAAAhAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEAIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAy6+yWeX6+++fPDAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMMMIMAAAP2++++uKAAAAAAAAAAAEMMMMMMEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQPyyyyiDqIr2+++++iAAAAAAAAAQX+++++vyyiAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA0CSy2++LQjCCCCCiAAAAAAAAAOCyy+++rAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA8CCCGe+ik2+iCCCzAAAAAAAACjCCCCSrAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEBPP/wD/AP8AA0zDDDDDAAAAAAAUQjDDDDTzAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQwwgAAAMkEMc888oAAAAAAYAE84wwwkAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAUAIAAAAAUAEAAAAAQoAAAAAgAAAAAAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAoQAAAAAAIAIAAAAAEAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA8AwAAAAAAgAEAAAAAAAAAAYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIAAIAAAAAQoAIAAAAAgAAAIAAAAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQIAA8AAAAAAoQIAAAAAQAAQoAAAAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAgAAAAoAAAAAAIcAAAAAAIAIAAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMAAAAMAAAAAAIAAAAAAAEQYAAAAAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEoAAAAEAAAAAAQA8AAAAAAMIAAAAAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAYwwgQ8YAAAAAAQIUIAAAAAEAAAAoAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIAAAAAAQAAAAAAEAsAAAAAoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAYAAAAAAQgAAAAAQAEIAAAQgAAAAgAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAAAAAAAAEAAAAAAsAIAAAEAAAAAIAAAAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAgAAAAAAIUAAAIAAAAAAAAAAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA0AAAAAAAAAQMAAAAAAAgAQAAAAAAgAAAAAUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEMMIQIMAAAAAAAAAwIIAAUAAsYAAAEAMgAAAAAQMIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQO+6CqOAAAAAAAAAAKSiSWAAWqAAAEiCCCySiSmamgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACKAAAAAAAAAAE+OOOOSACuKAAAAAAGOOOOOaAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAiAAAAAAAAACe+++++gA+++IAAAAAe+++++qAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAASAAAAAAAAACCCCCCCASCCCCAAAAAiCCCCCCAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQgAAAAAAAaCCCCCCoAiCCCCAAAAACCCCCCCAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAAAAe+++++6AU+++++AAAAA2+++++qAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGAAAAAAC++++++qA2+++++KAAAAW+++++qAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACqCCCCCCCCCCCGAECCCCCCiAAAAqCCCCCCAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAiAAAAAOOOOOOaAGOOOOOSAAAAAuOOOOOKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAe++++++AE++++++qAAAAA++++++qAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAe+++++qAG+++++6AAUAAA++++++oAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEAAAAAAgAAAwwwwwwAAQwwwwwgAAAIAA4wwwwwgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQ53fJJ5JAAAAAAAAAAAAAAAX7AAAAAAAAAAAAAAAAAQAFjvoAgAAVPJoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA3hAAQx/AAAAAAAAAAAAAE7/gAAEfoQAEMMMMMMoAc88FflYAAEB/oAEMMMMMIAAAAAEIAAAAAAAAAAEdNEloAAIAAAAAAAAAAAAAfoAAAA/vAAAAAAAAAAAAUAfsAAAXIAAU888888AE8889c/gAAMM/IAU88888oAAAAA7gAAAAAAAAAAA1vAVAQ3AAAAAAAAAAAAAAXoAAAAU/AAEEAAAAAAAAFAVrAAAVIAAwwwwwwgAQwwwZwfAAAFU/AAQwwwwwgAAIIAAAAAAAAAAAAAAEvAEoAAAAAAAAAAAAAAAAXoAAAAQvgpvlwAAAAAAQ5AA/AAARgAcEtQJ5ElIAAAAVAZ/AQgU/oAYF/oE9t/U/dkQgEVQ9ZAAAUdIAvAQIEdoAAAAAAAAAAAAA3AAAAAJvAErAAAAAAAAFZxx3pAABAU7ATJAnU4AAAAAVAQvg5AQ/gA7AVIQXAgAnAABpAXRAxIEXAfoA/AAoA/oAAAAAAAAAAAAAXoAAAAX5AArAAAAAAAARAAAVrAABAQtAAAAQDAAAAAAlAAfPIAE/gAAMFoADoAAzAAAoAUAAVoEgAAAA/AAAAVoAAAAAAAAAAAAAXFAAEN7gAQrAAFAAAAAJAAAQvIAVoU3IAEAtRlAAAAArAAQvgAU/oAlIUgALoAAHAAAoAUAABoQfAEAU/AAAAdgAAAAAAAAAAAEMf3JlVhAAA5/gA7gAAEn/oAA43bcGdAwja0lgAvMAAQB/kIAoAQB/NgXpJTY34AA1REk9ANZAXZAxb9A0rgtdU3hAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA/8QAAv/aAAwDAQACAAMAAAAQ88888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888884w088888888888888888888888888888888888888888888888888888888888888888888888888888888888888888sff7PX3mEEccdwW088888888888888888888888888888888888888888888888888888888888888888888888888888888888884ww8408Mu0888sM7888888888880888888880888888888888888888888888888888888888888888888888888888888888888CEMMMct/8AOuMMMMMO/PPPPPPPPOBTDDDDCzz7vPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPKfLDCEMIpIgENPPHFPPPPPPPPK9DDAAEMfPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPLERPPOIAP/XPIAAAM/PPPPPPPNwxDPPLB/PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPLDEshzjjrNcggz/AH3TzzzzzyxQoE1320rzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzj320wx1C7HCEEEETzzzzzwDj40kEEH3zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzygjzzzzzyjTLzzzzzxTzzzzizhbzzzzzjzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzBw7zzzzzxxrzzzzzzzzzzzjzz7zzzzyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzDzrzzzzzwzxrzzzzyzzzzzRzz7zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzgjyz7zzzzzzzrTzzzzxTzzxTzzzzzzzyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyjTzw7zzzzzxThbzzzzyzzyDTzz7zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyzzzzjzzzzzzzw7zzzzzxzyTzzz7zzzzyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyTzzzx7zzzzzzixTzzzzwjgzzzzbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzhzzzzyrzzzzzyjwLzzzzyzDzzzxbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyCgDCAyzDzzzzyxSrzzzzzwjzzzxbzzzzzjzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyjzzzzzzzzzzzzwyxTzzzzzTzzzzTzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzhTzzzzzyxTzzzzyxTjTzzyjzzzzxTzzzzyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyxTzzzzzzxjzzzzzzTzzzzzzzzzzzTzzzzyjzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzxjzzzzzzzzzTzzzzyzSzTzxTzzzzxzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzjTzzzzzzzzzxjzzzzxzzzzjzzzzzzTzzzzyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzjwyjjDzzzzzzzzzjzzzyzyxiDzzzTTzzzzzzyjDjTzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzxoIR4L7zzzzzzzzzzaazw7zzrbzzyybJYzyzyyhqpzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzw77zzzzzzzzzzjDDDDDbypDDzzzzzxjDDDDCLzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzxbzzzzzzzzypzzzzzxzw7zzTzzzzxTzzzzy7zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz7zzzzzzzzwIIIIIJLyoIIJbzzzzyoIIIIJbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyzzzzzzzzyY444447Tw4445rzzzzy4444457zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzLzzzzzzwIIIIIJbywIIIILzzzzwoIIIIJbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzrzzzzzyr77777z7x7777777zzzx7777777zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzy7777776oIIIIIbygIIIIIJ7zzzwIIAAABbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz7zzzzjLLLLLLbzrLLLLL6xzzzxrLLLLLbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzyzzzzyoIIIIIJTwIIIIIJbzDzzyoIIIIJbzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzjzzzx7777777y7777775zyzzzz777777zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzjzzzzzxzzzDDDDDDBzxDDDDDDTzzzTzzjDDDDDTzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzhdmm9/PvzzzzzzzzzzzzzzwmHzzzzzxjzwwwwwwxjzwzOHEwzzzyPEvwQwwwwxzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzwF/zyxsXzzzzzzzzzzzzzhFPzzzzFbjzzDDDDDBzyAAA+lfTzzjcNzzjDDDDDTzzzzzjzzzzzzzzzzzz8fiN7zDzzzzzzzzzzzzzwlbzzzwkHzzzzzzzzzzzz5QnbzzwlbzTzzzzzzzzzzzwu5HTzzpgNTzzzzzzzzzzzzwX7zzzzzzzzzzytWw/bw1Tzzzzzzzzzzzzyn7zzzz5XzjzBbzzzzzzz/w8HzzztbxjDDDDDDTzjDDBvANbzyvwPzzjDDDDDTzzJTzzzzzzzzzzzzzyhHz57zzzzzzzzzzzzzzzyHbzzzzpHw8H8LzzzzzzxvTxNzzzv7yb5tz+MScAAAAA8g9Hy7TwNTzz/EgBM+2QMN6b7iNLuvTzI7PzxHy7bj/AM8888888888888B28888/V84V88888888jPPPJ/88r+4xyZX8dqc88888f84D0z84Dc85c/+shu88R88f8A7CX/AA/6p341b4Hz5byHzzzzzzzzzzzzzylbzzzwFPzxXzzzzzzzyfzzw9Xzyv66PzzzyrXzzzzzwfzylU7ywPzziLv7xVTzxHzz77xb7yv757zzzgHz77yvzzzzzzzzzzzzzykPzzytlzz5XzjfTzzzq/zzzxPzzv7gHTzDxc/fzzzzwXzy4FzygNTxMbr7xVzzwnzz7bxb7z/a5XzjzgXzrbwPTzzzzzzzzzzyzYUkuOv/AM84vJ64DW88SlB888GN5iUDUuNQc/6sVg884z9S0se84/NzUBfzpEpC08vfY63ETDsZn8rFTIaN6LnWlz888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888/8QAJBEAAgICAgMAAgMBAAAAAAAAAAEQESAhMGAxQEFQUXCAkIH/2gAI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" alt="Dr. Alex Martinelli">
    <div class="brand-t">Dr. Alex Martinelli x Viviane Costa<span>Dermatologia · Medicina Estetica</span></div>
  </div>
  <div class="tbr" style="gap:6px;align-items:center"><span id="user-email" style="font-size:.6rem;color:rgba(201,168,76,.5);display:none"></span><button class="logout-btn" id="btn-logout" onclick="fazerLogout()" style="display:none">Sair</button>
    <button class="bt" id="btn-back" onclick="voltarLista()">Voltar</button>
    <button class="bt" id="btn-salvar" onclick="salvarPaciente()">Salvar</button>
    <button class="bt" style="background:rgba(255,255,255,.07);color:var(--silver)" onclick="window.print()">Imprimir</button>
  </div>
</div>

<div id="tela-lista">
  <div class="lwrap">
    <div class="lhdr">
      <div><div class="ltit">Pacientes</div><div class="lsub" id="lsub">Carregando...</div></div>
      <button class="btn-nova" onclick="novoPaciente()">+ Novo Paciente</button>
    </div>
    <input type="text" class="si" id="busca-lista" placeholder="Buscar pelo nome..." oninput="filtrarLista(this.value)">
    <div id="lista-cont"><div style="text-align:center;padding:30px;color:var(--silver)">Conectando...</div></div>
  </div>
</div>

<div id="tela-ficha">
  <div class="tabs">
    <button class="tab on" onclick="aba('dados',this)">Dados</button>
    <button class="tab" onclick="aba('tratamentos',this)">Tratamentos</button>
    <button class="tab" onclick="aba('medidas',this)">Medidas</button>
    <button class="tab" onclick="aba('evolucao',this)">Evolucao</button>
    <button class="tab" onclick="aba('fotos',this)">Fotos</button>
    <button class="tab" onclick="aba('receituario',this)">Receituario</button>
    <button class="tab" onclick="aba('faturamento',this)">Faturamento</button>
    <button class="tab" onclick="aba('graficos',this)">Graficos</button>
    <button class="tab" onclick="aba('protocolos',this)">Protocolos</button>
    <button class="tab" onclick="aba('comparativo',this)">Comparativo</button>
    <button class="tab" onclick="aba('score',this)">Score IA</button>
    <button class="tab" onclick="aba('agenda',this)">🗓️ Agenda</button>
  </div>
  <div class="main">

    <!-- DADOS -->
    <div id="p-dados" class="panel on">
      <div style="background:var(--n3);border:1.5px solid var(--bd);border-radius:10px;padding:10px 14px;margin-bottom:11px;display:flex;gap:8px;align-items:center">
        <span>Buscar:</span>
        <input type="text" id="brap" placeholder="Buscar outro paciente..." oninput="buscaRap(this.value)" style="flex:1;border:none;background:none;font-family:Outfit,sans-serif;font-size:.8rem;color:var(--white);outline:none">
      </div>
      <div id="brap-res" style="display:none;background:var(--n3);border:1.5px solid var(--gold);border-radius:10px;margin-bottom:11px;overflow:hidden;max-height:220px;overflow-y:auto"></div>
      <div class="hero">
        <div class="avatar" id="av">?</div>
        <div style="flex:1;min-width:0"><div class="h-nome" id="hn">Novo Paciente</div><div class="h-meta" id="hm">Preencha os dados abaixo</div></div>
        <div><div class="h-pct" id="pct">0%</div><div class="h-pl">FICHA</div></div>
      </div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">👤</div><div class="card-tit">Dados Pessoais</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div class="grid g2">
            <div class="field full"><label>Nome Completo</label><input type="text" class="fi" id="nome" placeholder="Nome do paciente" oninput="atualizarHero()"></div>
            <div class="field"><label>Data de Nascimento</label><input type="date" class="fi" id="nasc" onchange="atualizarHero()"></div>
            <div class="field"><label>Idade</label><input type="number" class="fi" id="idade" readonly placeholder="--"></div>
            <div class="field"><label>Telefone</label><input type="tel" class="fi" id="tel" placeholder="(00) 00000-0000"></div>
            <div class="field"><label>E-mail</label><input type="email" class="fi" id="email" placeholder="email@exemplo.com"></div>
            <div class="field"><label>CPF</label><input type="text" class="fi" id="cpf" placeholder="000.000.000-00"></div>
            <div class="field"><label>Profissao</label><input type="text" class="fi" id="prof" placeholder="Profissao"></div>
            <div class="field"><label>Como nos conheceu</label>
              <select class="fs" id="orig"><option value="">Selecione</option><option>Instagram</option><option>Indicacao</option><option>Google</option><option>WhatsApp</option><option>Outro</option></select>
            </div>
            <div class="field"><label>Data de Inicio</label><input type="date" class="fi" id="inicio"></div>
            <div class="field"><label>Responsavel</label>
              <select class="fs" id="medico"><option value="">Selecione</option><option>Dr. Alex Martinelli</option><option>Viviane Costa</option><option>Protocolo Conjunto</option></select>
            </div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">🏥</div><div class="card-tit">Anamnese e Saude</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div id="alertas"></div>
          <div class="togs" id="saude-tog">
            <div class="tog" onclick="alerta(this,'Marcapasso - RF e Ultrassom contraindicados!','err')">Marcapasso</div>
            <div class="tog" onclick="alerta(this,'Historico oncologico - requer liberacao medica.','err')">Oncologico</div>
            <div class="tog" onclick="alerta(this,'Trombose - drenagem contraindicada.','err')">Trombose</div>
            <div class="tog" onclick="alerta(this,'Doenca cardiovascular - liberacao medica.','err')">Cardiaco</div>
            <div class="tog" onclick="alerta(this,'Epilepsia - evitar estimulos eletricos.','warn')">Epilepsia</div>
            <div class="tog" onclick="alerta(this,'Hipertensao - monitorar PA antes da sessao.','warn')">Hipertensao</div>
            <div class="tog" onclick="alerta(this,'Diabetes - atencao a sensibilidade termica.','warn')">Diabetes</div>
            <div class="tog" onclick="this.classList.toggle('on')">Varizes</div>
            <div class="tog" onclick="this.classList.toggle('on')">Gravidez</div>
            <div class="tog" onclick="this.classList.toggle('on')">Lactacao</div>
            <div class="tog" onclick="this.classList.toggle('on')">Metal implantado</div>
            <div class="tog" onclick="this.classList.toggle('on')">Nenhuma</div>
          </div>
          <div class="grid g2" style="margin-top:11px">
            <div class="field"><label>Medicamentos</label><textarea class="fta" id="meds" placeholder="Liste os medicamentos..."></textarea></div>
            <div class="field"><label>Alergias</label><textarea class="fta" id="alerg" placeholder="Alergias conhecidas..."></textarea></div>
            <div class="field"><label>Cirurgias</label><textarea class="fta" id="ciru" placeholder="Cirurgias e quando..."></textarea></div>
            <div class="field"><label>Tratamentos Anteriores</label><textarea class="fta" id="trat-ant" placeholder="O que ja foi feito..."></textarea></div>
          </div>
          <div class="div"></div>
          <div class="grid g2">
            <div class="field"><label>Atividade Fisica</label><select class="fs" id="atv"><option value="">Selecione</option><option>Nao pratica</option><option>1-2x/semana</option><option>3-4x/semana</option><option>5x ou mais</option></select></div>
            <div class="field"><label>Alimentacao</label><select class="fs" id="alim"><option value="">Selecione</option><option>Muito saudavel</option><option>Moderada</option><option>Processados frequentes</option></select></div>
            <div class="field"><label>Peso (kg)</label><input type="number" class="fi" id="peso" step="0.1" placeholder="0.0" oninput="calcImc()"></div>
            <div class="field"><label>Altura (cm)</label><input type="number" class="fi" id="alt" placeholder="000" oninput="calcImc()"></div>
            <div class="field"><label>IMC</label><input type="text" class="fi" id="imc" readonly placeholder="--"></div>
            <div class="field"><label>Gordura (%)</label><input type="number" class="fi" id="gord" step="0.1" placeholder="0.0"></div>
            <div class="field full"><label>Objetivo Clinico</label><textarea class="fta" id="obj" placeholder="O que o paciente deseja alcançar..."></textarea></div>
          </div>
        </div>
      </div>
    </div>

    <!-- TRATAMENTOS -->
    <div id="p-tratamentos" class="panel">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px">
        <div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white)">Sessoes por Tratamento</div>
          <div style="font-size:.68rem;color:var(--silver);margin-top:2px">Cada tratamento com seus parametros e historico</div>
        </div>
        <button class="btn btn-g" onclick="abrirModalSessao()">+ Registrar Sessao</button>
      </div>
      <div id="trats-cont">
        <div style="text-align:center;padding:40px;color:var(--silver)">
          <div style="font-size:2rem;margin-bottom:8px">+</div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white);margin-bottom:4px">Nenhuma sessao registrada</div>
          <div style="font-size:.72rem">Clique em Registrar Sessao para comecar.</div>
        </div>
      </div>
    </div>

    <!-- MEDIDAS -->
    <div id="p-medidas" class="panel">
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">📏</div><div class="card-tit">Evolucao das Medidas (cm)</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:11px;flex-wrap:wrap;gap:7px">
            <p style="font-size:.7rem;color:var(--silver)">Sistema calcula evolucao automaticamente.</p>
            <button class="btn btn-g" onclick="addColMed()">+ Sessao</button>
          </div>
          <div style="overflow-x:auto">
            <table class="mtable" id="med-t">
              <thead><tr id="med-head"><th>Regiao</th><th>Inicial</th><th>Sessao 1</th><th>Sessao 2</th><th>Sessao 3</th><th>Total</th></tr></thead>
              <tbody id="med-body"></tbody>
            </table>
          </div>
          <div class="gwrap"><div class="gtit">REDUCAO POR REGIAO (cm)</div><div class="gbars" id="graf"></div></div>
        </div>
      </div>
    </div>

    <!-- EVOLUCAO -->
    <div id="p-evolucao" class="panel">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;flex-wrap:wrap;gap:8px">
        <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white)">Evolução Clínica</div>
        <button class="btn btn-g" onclick="gerarRelatorio()">📄 Relatório do Paciente</button>
      </div>
      <div class="kpis" id="kpis-evol"></div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">📊</div><div class="card-tit">Resumo de Sessoes por Tratamento</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div style="overflow-x:auto">
            <table class="evol-table" id="evol-resumo">
              <thead><tr><th>Tratamento</th><th>Sessoes</th><th>Ultima Sessao</th><th>Proxima</th><th>Resultado</th></tr></thead>
              <tbody id="evol-body"></tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">⭐</div><div class="card-tit">Avaliacao de Resultados</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div class="srow"><span class="srow-l">Reducao de medidas</span><div class="stars" id="sc0"><span class="star" onclick="setStar(0,1)">*</span><span class="star" onclick="setStar(0,2)">*</span><span class="star" onclick="setStar(0,3)">*</span><span class="star" onclick="setStar(0,4)">*</span><span class="star" onclick="setStar(0,5)">*</span></div></div>
          <div class="srow"><span class="srow-l">Melhora da celulite</span><div class="stars" id="sc1"><span class="star" onclick="setStar(1,1)">*</span><span class="star" onclick="setStar(1,2)">*</span><span class="star" onclick="setStar(1,3)">*</span><span class="star" onclick="setStar(1,4)">*</span><span class="star" onclick="setStar(1,5)">*</span></div></div>
          <div class="srow"><span class="srow-l">Firmeza / flacidez</span><div class="stars" id="sc2"><span class="star" onclick="setStar(2,1)">*</span><span class="star" onclick="setStar(2,2)">*</span><span class="star" onclick="setStar(2,3)">*</span><span class="star" onclick="setStar(2,4)">*</span><span class="star" onclick="setStar(2,5)">*</span></div></div>
          <div class="srow"><span class="srow-l">Satisfacao geral</span><div class="stars" id="sc3"><span class="star" onclick="setStar(3,1)">*</span><span class="star" onclick="setStar(3,2)">*</span><span class="star" onclick="setStar(3,3)">*</span><span class="star" onclick="setStar(3,4)">*</span><span class="star" onclick="setStar(3,5)">*</span></div></div>
        </div>
      </div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">📝</div><div class="card-tit">Diario de Evolucao</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div style="display:flex;gap:7px;margin-bottom:11px;flex-wrap:wrap">
            <textarea id="nova-obs" placeholder="Registre uma observacao clinica..." style="flex:1;padding:8px 11px;border:1.5px solid var(--bd);border-radius:7px;font-family:Outfit,sans-serif;font-size:.78rem;min-height:62px;resize:vertical;min-width:160px;background:var(--n4);color:var(--white);outline:none"></textarea>
            <button class="btn btn-m" onclick="addObs()" style="align-self:flex-end">+ Registrar</button>
          </div>
          <div class="tl" id="tl">
            <div class="tli"><div class="tld"></div><div class="tldt">Aguardando</div><div class="tltx" style="font-style:italic">As observacoes aparecerao aqui.</div></div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">💡</div><div class="card-tit">Recomendacoes</div><div class="card-arr">v</div></div>
        <div class="card-b">
          <div class="grid g2">
            <div class="field"><label>Proxima Sessao</label><input type="date" class="fi" id="prox-sess"></div>
            <div class="field"><label>Frequencia</label><select class="fs" id="freq"><option value="">Selecione</option><option>1x por semana</option><option>2x por semana</option><option>A cada 15 dias</option><option>1x por mes</option></select></div>
            <div class="field full"><label>Orientacoes</label><textarea class="fta" id="orient" placeholder="Cuidados, produtos, habitos..."></textarea></div>
          </div>
        </div>
      </div>
    </div>

    <!-- FOTOS -->
    <div id="p-fotos" class="panel">
      <div class="card">
        <div class="card-h" onclick="togCard(this)"><div class="card-ico">📸</div><div class="card-tit">Registro Fotografico - Antes e Depois</div><div class="card-arr">v</div></div>
        <div class="card-b"><div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(125px,1fr));gap:9px" id="fotos-grid"></div></div>
      </div>
    </div>

    <!-- RECEITUARIO -->
    <div id="p-receituario" class="panel">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px">
        <div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white)">Receituario Medico</div>
          <div style="font-size:.68rem;color:var(--silver);margin-top:2px">Dr. Alex Martinelli - CRM/RJ 5273573-6</div>
        </div>
        <button class="btn btn-g" onclick="abrirModalRx()">+ Nova Receita</button>
      </div>
      <div id="rx-list"><div style="text-align:center;padding:35px;color:var(--silver);font-size:.78rem">Nenhuma receita emitida ainda.</div></div>
    </div>

    <!-- FATURAMENTO -->
    <div id="p-faturamento" class="panel">
      <div class="fsum" id="fsum"></div>
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:11px">
        <div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white)">Pagamentos</div>
        <button class="btn btn-g" onclick="abrirModalPag()">+ Registrar Pagamento</button>
      </div>
      <div id="pag-list"></div>
      <div id="pag-empty" style="text-align:center;padding:30px;color:var(--silver);font-size:.78rem">Nenhum pagamento registrado.</div>
    </div>

    <!-- GRAFICOS -->
    <div id="p-graficos" class="panel">
      <div style="font-family:Cormorant Garamond,serif;font-size:1.4rem;color:var(--white);margin-bottom:4px">Analises e Graficos</div>
      <div style="font-size:.68rem;color:var(--silver);margin-bottom:16px">Visao inteligente de tratamentos e evolucao</div>
      <div class="kpis" id="kpis-graf"></div>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px" id="graf-grid">
        <div style="background:var(--n3);border:1px solid var(--bd);border-radius:12px;padding:16px">
          <div style="font-size:.58rem;letter-spacing:2px;color:var(--gold);text-transform:uppercase;margin-bottom:12px">Tratamentos Mais Realizados</div>
          <div id="graf-trats" style="display:flex;flex-direction:column;gap:7px"></div>
        </div>
        <div style="background:var(--n3);border:1px solid var(--bd);border-radius:12px;padding:16px">
          <div style="font-size:.58rem;letter-spacing:2px;color:var(--gold);text-transform:uppercase;margin-bottom:12px">Progresso Clinico</div>
          <div id="graf-prog" style="display:flex;flex-direction:column;gap:9px"></div>
        </div>
      </div>
    </div>

    <!-- PROTOCOLOS -->
    <div id="p-protocolos" class="panel">
      <div style="display:flex;align-items:flex-start;justify-content:space-between;flex-wrap:wrap;gap:10px;margin-bottom:16px">
        <div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.5rem;color:var(--white);margin-bottom:4px">Protocolos Premium</div>
          <div style="font-size:.68rem;color:var(--silver)">Protocolos casados Dr. Alex Martinelli x Viviane Costa</div>
        </div>
        <button class="ia-btn" onclick="rodarIA()" id="ia-btn">✦ Sugestão IA</button>
      </div>
      <!-- PAINEL IA -->
      <div class="ia-wrap" id="ia-painel" style="display:none">
        <div class="ia-header">
          <div class="ia-icon">✦</div>
          <div><div class="ia-title">Intelectus IA — Sugestão de Protocolo</div><div class="ia-sub">Análise baseada no perfil clínico deste paciente</div></div>
        </div>
        <div class="ia-loading" id="ia-loading" style="display:none">
          <div class="ia-dot"></div><div class="ia-dot"></div><div class="ia-dot"></div>
          <span>Analisando perfil clínico...</span>
        </div>
        <div class="ia-result" id="ia-result"></div>
      </div>
      <div class="prot-cats">
        <button class="pcat on" onclick="filtroProt(this,'todos')">Todos</button>
        <button class="pcat" onclick="filtroProt(this,'gordura')">Gordura</button>
        <button class="pcat" onclick="filtroProt(this,'flacidez')">Flacidez</button>
        <button class="pcat" onclick="filtroProt(this,'celulite')">Celulite</button>
        <button class="pcat" onclick="filtroProt(this,'rejuvenescimento')">Rejuvenescimento</button>
      </div>
      <div class="pgrid2" id="prot-grid"></div>
    </div>

    <!-- AGENDA -->
    <div id="p-agenda" class="panel">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;flex-wrap:wrap;gap:8px">
        <div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white)">Agenda Semanal</div>
          <div style="font-size:.68rem;color:var(--silver);margin-top:2px" id="agenda-periodo"></div>
        </div>
        <div style="display:flex;gap:8px;align-items:center;flex-wrap:wrap">
          <button class="btn btn-m" onclick="semanaAnterior()">← Semana</button>
          <button class="btn btn-m" onclick="semanaHoje()">Hoje</button>
          <button class="btn btn-m" onclick="proximaSemana()">Semana →</button>
          <button class="btn btn-g" onclick="abrirModalAgenda()">+ Agendar</button>
        </div>
      </div>
      <!-- KPIs da semana -->
      <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:9px;margin-bottom:14px" id="agenda-kpis"></div>
      <!-- Calendário semanal -->
      <div style="overflow-x:auto">
        <div id="agenda-grid" style="min-width:600px"></div>
      </div>
      <!-- Lista do dia selecionado -->
      <div id="agenda-dia-detalhe" style="margin-top:14px;display:none">
        <div style="font-size:.58rem;letter-spacing:2px;color:var(--gold);text-transform:uppercase;font-weight:700;margin-bottom:10px" id="agenda-dia-titulo"></div>
        <div id="agenda-dia-lista"></div>
      </div>
    </div>

    <!-- COMPARATIVO DE PARÂMETROS -->
    <div id="p-comparativo" class="panel">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;flex-wrap:wrap;gap:8px">
        <div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white)">Comparativo de Parâmetros</div>
          <div style="font-size:.68rem;color:var(--silver);margin-top:2px">Compare parâmetros técnicos entre sessões do mesmo tratamento</div>
        </div>
        <select class="fs" id="comp-trat-sel" onchange="renderComparativo(this.value)" style="width:auto;min-width:180px">
          <option value="">Selecione o tratamento</option>
        </select>
      </div>
      <div id="comp-content">
        <div style="text-align:center;padding:40px;color:var(--silver)">
          <div style="font-size:2rem;margin-bottom:8px">📊</div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white);margin-bottom:4px">Selecione um tratamento</div>
          <div style="font-size:.72rem">Escolha acima para ver o comparativo entre sessões</div>
        </div>
      </div>
    </div>

    <!-- SCORE POR PROTOCOLO -->
    <div id="p-score" class="panel">
      <div style="margin-bottom:14px">
        <div style="font-family:Cormorant Garamond,serif;font-size:1.3rem;color:var(--white);margin-bottom:4px">Score de Resultado por Protocolo</div>
        <div style="font-size:.68rem;color:var(--silver)">Análise automática de eficácia baseada nas sessões e avaliações</div>
      </div>
      <div class="kpis" id="score-kpis" style="margin-bottom:16px"></div>
      <div class="score-wrap" id="score-grid">
        <div style="text-align:center;padding:40px;color:var(--silver);grid-column:1/-1">
          <div style="font-size:2rem;margin-bottom:8px">🏆</div>
          <div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white);margin-bottom:4px">Nenhuma sessão registrada</div>
          <div style="font-size:.72rem">Registre sessões para ver o score de cada protocolo</div>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- MODAL SESSAO -->
<div class="ov" id="ov-sess" onclick="if(event.target===this)fechaModal('ov-sess')">
  <div class="modal">
    <div class="mhdr"><div class="mtit">Registrar Sessao</div><button class="mclose" onclick="fechaModal('ov-sess')">X</button></div>
    <div class="sdiv">Selecione o Tratamento</div>
    <div class="tpick-grid" id="tpick-grid"></div>
    <input type="hidden" id="sess-trat">
    <div class="grid g2">
      <div class="field"><label>Data da Sessao</label><input type="date" class="fi" id="sess-data"></div>
      <div class="field"><label>No da Sessao</label><input type="number" class="fi" id="sess-num" min="1" placeholder="1"></div>
      <div class="field"><label>Proxima Sessao</label><input type="date" class="fi" id="sess-prox"></div>
      <div class="field"><label>Reacao do Paciente</label>
        <select class="fs" id="sess-reac"><option value="">Selecione</option><option>Muito bem</option><option>Leve desconforto</option><option>Desconforto moderado</option><option>Interrompido</option></select>
      </div>
      <div class="field"><label>Resultado (1-5)</label>
        <select class="fs" id="sess-res"><option value="">Selecione</option><option value="1">1 - Insuficiente</option><option value="2">2 - Regular</option><option value="3">3 - Bom</option><option value="4">4 - Muito Bom</option><option value="5">5 - Excelente</option></select>
      </div>
    </div>
    <div class="sdiv">Parametros do Tratamento</div>
    <div id="modal-params" style="display:grid;grid-template-columns:repeat(auto-fill,minmax(130px,1fr));gap:8px;margin-bottom:10px"></div>
    <div class="field"><label>Observacoes Clinicas</label><textarea class="fta" id="sess-obs" placeholder="Evolucao, ajustes, resposta ao tratamento..."></textarea></div>
    <div class="mact">
      <button class="btn btn-g" onclick="salvarSessao()">Salvar Sessao</button>
      <button class="btn btn-m" onclick="fechaModal('ov-sess')">Cancelar</button>
    </div>
  </div>
</div>

<!-- MODAL PAGAMENTO -->
<div class="ov" id="ov-pag" onclick="if(event.target===this)fechaModal('ov-pag')">
  <div class="modal">
    <div class="mhdr"><div class="mtit">Registrar Pagamento</div><button class="mclose" onclick="fechaModal('ov-pag')">X</button></div>
    <div class="grid g2">
      <div class="field full"><label>Nome do Paciente que Pagou</label><input type="text" class="fi" id="pag-pac" placeholder="Nome de quem pagou"></div>
      <div class="field"><label>Procedimento</label><input type="text" class="fi" id="pag-proc" placeholder="Ex: Botox, Heccus..."></div>
      <div class="field"><label>Valor (R$)</label><input type="number" class="fi" id="pag-val" placeholder="0,00" step="0.01"></div>
      <div class="field"><label>Forma de Pagamento</label>
        <select class="fs" id="pag-forma"><option value="">Selecione</option><option>Pix</option><option>Credito 1x</option><option>Credito 2x</option><option>Credito 3x</option><option>Credito 6x</option><option>Credito 12x</option><option>Debito</option><option>Dinheiro</option></select>
      </div>
      <div class="field"><label>Status</label>
        <select class="fs" id="pag-status"><option value="pago">Pago</option><option value="pendente">Pendente</option><option value="parcelado">Parcelado</option></select>
      </div>
      <div class="field"><label>Data</label><input type="date" class="fi" id="pag-data"></div>
      <div class="field full"><label>Observacao</label><input type="text" class="fi" id="pag-obs" placeholder="Opcional..."></div>
    </div>
    <div class="mact">
      <button class="btn btn-g" onclick="salvarPag()">Salvar</button>
      <button class="btn btn-m" onclick="fechaModal('ov-pag')">Cancelar</button>
    </div>
  </div>
</div>

<!-- MODAL RECEITA -->
<div class="ov" id="ov-rx" onclick="if(event.target===this)fechaModal('ov-rx')">
  <div class="modal" style="width:600px">
    <div class="mhdr"><div class="mtit">Nova Receita Medica</div><button class="mclose" onclick="fechaModal('ov-rx')">X</button></div>
    <div class="grid g2">
      <div class="field full"><label>Nome do Paciente</label><input type="text" class="fi" id="rx-pac" placeholder="Nome do paciente"></div>
      <div class="field"><label>Data</label><input type="date" class="fi" id="rx-data"></div>
      <div class="field"><label>Idade</label><input type="text" class="fi" id="rx-idade" placeholder="Ex: 35 anos"></div>
    </div>
    <div class="sdiv">Medicamentos</div>
    <div id="rx-meds-wrap"></div>
    <button class="btn btn-m" style="margin-bottom:10px" onclick="addMedRow()">+ Medicamento</button>
    <div class="field"><label>Orientacoes Gerais</label><textarea class="fta" id="rx-ori" placeholder="Restricoes, cuidados, retorno..."></textarea></div>
    <div class="mact">
      <button class="btn btn-g" onclick="salvarRx()">Salvar e Visualizar</button>
      <button class="btn btn-m" onclick="fechaModal('ov-rx')">Cancelar</button>
    </div>
  </div>
</div>

<!-- MODAL AGENDAMENTO -->
<div class="ov" id="ov-agenda" onclick="if(event.target===this)fechaModal('ov-agenda')">
  <div class="modal" style="width:560px">
    <div class="mhdr">
      <div class="mtit" id="agenda-modal-title">🗓️ Novo Agendamento</div>
      <button class="mclose" onclick="fechaModal('ov-agenda')">X</button>
    </div>
    <input type="hidden" id="agenda-edit-id">
    <div class="grid g2">
      <div class="field full">
        <label>Paciente</label>
        <input type="text" class="fi" id="ag-pac" placeholder="Nome do paciente" list="ag-pac-list">
        <datalist id="ag-pac-list"></datalist>
      </div>
      <div class="field">
        <label>Data</label>
        <input type="date" class="fi" id="ag-data">
      </div>
      <div class="field">
        <label>Horário</label>
        <input type="time" class="fi" id="ag-hora">
      </div>
      <div class="field">
        <label>Duração</label>
        <select class="fs" id="ag-dur">
          <option value="30">30 min</option>
          <option value="45">45 min</option>
          <option value="60" selected>1 hora</option>
          <option value="90">1h30</option>
          <option value="120">2 horas</option>
        </select>
      </div>
      <div class="field">
        <label>Procedimento</label>
        <select class="fs" id="ag-proc">
          <option value="">Selecione</option>
        </select>
      </div>
      <div class="field">
        <label>Profissional</label>
        <select class="fs" id="ag-prof">
          <option value="Dr. Alex Martinelli">Dr. Alex Martinelli</option>
          <option value="Viviane Costa">Viviane Costa</option>
          <option value="Ambos">Protocolo Conjunto</option>
        </select>
      </div>
      <div class="field">
        <label>Status</label>
        <select class="fs" id="ag-status">
          <option value="agendado">Agendado</option>
          <option value="confirmado">Confirmado</option>
          <option value="realizado">Realizado</option>
          <option value="cancelado">Cancelado</option>
          <option value="faltou">Faltou</option>
        </select>
      </div>
      <div class="field full">
        <label>Observação</label>
        <textarea class="fta" id="ag-obs" placeholder="Informações adicionais..."></textarea>
      </div>
    </div>
    <!-- Mensagem WhatsApp -->
    <div style="background:rgba(37,211,102,.08);border:1px solid rgba(37,211,102,.25);border-radius:9px;padding:12px 14px;margin-top:10px">
      <div style="font-size:.55rem;letter-spacing:2px;color:#25d366;text-transform:uppercase;font-weight:700;margin-bottom:8px">📱 Mensagem WhatsApp</div>
      <div id="ag-wamsg" style="font-size:.74rem;color:var(--silver);line-height:1.6;margin-bottom:9px"></div>
      <button class="btn" style="background:rgba(37,211,102,.15);color:#25d366;border:1px solid rgba(37,211,102,.3);font-size:.65rem" onclick="copiarWA()">📋 Copiar Mensagem</button>
    </div>
    <div class="mact" style="margin-top:14px">
      <button class="btn btn-g" onclick="salvarAgenda()">Salvar</button>
      <button class="btn" style="background:rgba(224,117,117,.12);color:var(--red);border:1px solid rgba(224,117,117,.25)" id="ag-del-btn" onclick="deletarAgenda()" style="display:none">🗑️ Excluir</button>
      <button class="btn btn-m" onclick="fechaModal('ov-agenda')">Cancelar</button>
    </div>
  </div>
</div>

<!-- MODAL RELATÓRIO PDF -->
<div class="ov" id="ov-relatorio" onclick="if(event.target===this)fechaModal('ov-relatorio')">
  <div class="modal" style="width:720px;max-height:92vh">
    <div class="mhdr">
      <div class="mtit">📄 Relatório de Evolução</div>
      <button class="mclose" onclick="fechaModal('ov-relatorio')">X</button>
    </div>
    <div id="relatorio-content"></div>
    <div class="mact">
      <button class="btn btn-g" onclick="window.print()">🖨️ Imprimir / Salvar PDF</button>
      <button class="btn btn-m" onclick="fechaModal('ov-relatorio')">Fechar</button>
    </div>
  </div>
</div>

<!-- MODAL VER RECEITA -->
<div class="ov" id="ov-rx-view" onclick="if(event.target===this)fechaModal('ov-rx-view')">
  <div class="modal" style="width:600px">
    <div class="mhdr"><div class="mtit">Receita Medica</div><button class="mclose" onclick="fechaModal('ov-rx-view')">X</button></div>
    <div id="rx-preview-content"></div>
    <div class="mact">
      <button class="btn btn-g" onclick="window.print()">Imprimir</button>
      <button class="btn btn-m" onclick="fechaModal('ov-rx-view')">Fechar</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
// =============================================
// DADOS DOS TRATAMENTOS
// =============================================
var TRAT_PROF = {
  'RF Microagulhada':'Dr. Alex Martinelli',
  'Botox':'Dr. Alex Martinelli',
  'Lipo de Papada':'Dr. Alex Martinelli',
  'Blefaroplastia':'Dr. Alex Martinelli',
  'Endolaser':'Dr. Alex Martinelli',
  'Enzimas':'Dr. Alex Martinelli',
  'HIFU':'Dr. Alex Martinelli',
  'Eleva':'Dr. Alex Martinelli',
  'Peeling Quimico':'Dr. Alex Martinelli',
  'PRP':'Dr. Alex Martinelli',
  'Fios':'Dr. Alex Martinelli',
  'Carboxiterapia CO2':'Dr. Alex Martinelli',
  'Mesoterapia Capilar':'Dr. Alex Martinelli',
  'Preenchimento':'Dr. Alex Martinelli',
  'Criofrequencia':'Viviane Costa',
  'Drenagem Linfatica':'Viviane Costa',
  'Heccus Turbo':'Viviane Costa',
  'Corrente Aussie':'Viviane Costa',
  'Duet':'Viviane Costa',
  'Endermologia':'Viviane Costa',
  'Limpeza de Pele':'Viviane Costa'
};

var TRAT_ICONS = {
  'RF Microagulhada':'🔥',
  'Botox':'💉',
  'Lipo de Papada':'✂️',
  'Blefaroplastia':'👁️',
  'Endolaser':'⚡',
  'Enzimas':'🌿',
  'HIFU':'🔊',
  'Eleva':'💎',
  'Peeling Quimico':'🧪',
  'PRP':'🩸',
  'Fios':'🧵',
  'Carboxiterapia CO2':'💨',
  'Mesoterapia Capilar':'🧖',
  'Preenchimento':'💋',
  'Criofrequencia':'❄️',
  'Drenagem Linfatica':'💧',
  'Heccus Turbo':'🌊',
  'Corrente Aussie':'🔋',
  'Duet':'⚙️',
  'Endermologia':'🚫',
  'Limpeza de Pele':'✨'
};

var TRAT_CORES = {
  'RF Microagulhada':'#f48fb1','Botox':'#64b5f6','Lipo de Papada':'#ffb74d',
  'Blefaroplastia':'#80cbc4','Endolaser':'#ef9a9a','Enzimas':'#ffcc80',
  'HIFU':'#4fc3f7','Eleva':'#b39ddb','Peeling Quimico':'#80deea',
  'PRP':'#ef9a9a','Fios':'#ce93d8','Carboxiterapia CO2':'#b0bec5',
  'Mesoterapia Capilar':'#a5d6a7','Preenchimento':'#f48fb1',
  'Criofrequencia':'#80cbc4','Drenagem Linfatica':'#a5d6a7',
  'Heccus Turbo':'#c9a84c','Corrente Aussie':'#ce93d8',
  'Duet':'#90caf9','Endermologia':'#ffb74d','Limpeza de Pele':'#fff176'
};

var TRAT_DEFS = {
  'RF Microagulhada':[{l:'Energia',u:'mJ'},{l:'Profundidade 1',u:'mm'},{l:'Profundidade 2',u:'mm'},{l:'Passes',u:'x'},{l:'Cobertura',u:'%'},{l:'Modo',u:''}],
  'Botox':[{l:'Produto',u:''},{l:'Dose total',u:'U'},{l:'Diluicao',u:'U/ml'},{l:'Glabela',u:'U'},{l:'Frontalis',u:'U'},{l:'Pes de galinha',u:'U'},{l:'Outras areas',u:''},{l:'Lote',u:''}],
  'Lipo de Papada':[{l:'Tecnica',u:''},{l:'Anestesia',u:''},{l:'Sol. tumescente',u:'ml'},{l:'Canula',u:'mm'},{l:'Pressao',u:'mmHg'},{l:'Vol. aspirado',u:'ml'}],
  'Blefaroplastia':[{l:'Tecnica',u:''},{l:'Anestesia',u:''},{l:'Fio de sutura',u:''},{l:'Palpebra sup D',u:'mm'},{l:'Palpebra sup E',u:'mm'},{l:'Palpebra inf',u:''},{l:'Duracao',u:'min'}],
  'Endolaser':[{l:'Comp. onda',u:'nm'},{l:'Potencia',u:'W'},{l:'Fluencia',u:'J/cm2'},{l:'Fibra optica',u:'um'},{l:'Modo',u:''}],
  'Enzimas':[{l:'Enzima',u:''},{l:'Concentracao',u:'UTR'},{l:'Volume',u:'ml'},{l:'Area',u:''},{l:'Tecnica',u:''}],
  'HIFU':[{l:'Frequencia',u:'MHz'},{l:'Profundidade',u:'mm'},{l:'Energia',u:'J'},{l:'Linhas',u:''},{l:'Regiao',u:''}],
  'Eleva':[{l:'Tecnica',u:''},{l:'Produto',u:''},{l:'Volume',u:'ml'},{l:'Area',u:''},{l:'Lote',u:''}],
  'Peeling Quimico':[{l:'Ativo',u:''},{l:'Concentracao',u:'%'},{l:'Tempo',u:'min'},{l:'Regiao',u:''}],
  'PRP':[{l:'Tecnica',u:''},{l:'Vol. coletado',u:'ml'},{l:'Centrifugacao',u:'rpm'},{l:'Vol. injetado',u:'ml'},{l:'Area',u:''},{l:'Ativador',u:''}],
  'Fios':[{l:'Tipo de fio',u:''},{l:'Espessura',u:'mm'},{l:'Comprimento',u:'cm'},{l:'Quantidade',u:'un'},{l:'Area',u:''},{l:'Anestesia',u:''}],
  'Carboxiterapia CO2':[{l:'Fluxo CO2',u:'ml/min'},{l:'Volume',u:'ml'},{l:'Duracao',u:'min'},{l:'Area',u:''},{l:'Profundidade',u:'mm'}],
  'Mesoterapia Capilar':[{l:'Produto',u:''},{l:'Concentracao',u:''},{l:'Volume',u:'ml'},{l:'Tecnica',u:''},{l:'Agulha',u:'mm'}],
  'Preenchimento':[{l:'Produto',u:''},{l:'Volume',u:'ml'},{l:'Area',u:''},{l:'Tecnica',u:''},{l:'Lote',u:''}],
  'Criofrequencia':[{l:'Temperatura',u:'C'},{l:'RF Intensidade',u:'%'},{l:'Duracao',u:'min'},{l:'Ciclos',u:'x'},{l:'Regiao',u:''}],
  'Drenagem Linfatica':[{l:'Tecnica',u:''},{l:'Duracao',u:'min'},{l:'Regiao',u:''},{l:'Nivel pressao',u:''}],
  'Heccus Turbo':[{l:'Intens. Ultrassom',u:'W'},{l:'Freq. Corrente',u:'Hz'},{l:'Duracao',u:'min'},{l:'Ativo',u:''},{l:'Poliaridade',u:''},{l:'Diluicao',u:'ml'}],
  'Corrente Aussie':[{l:'Frequencia',u:'Hz'},{l:'Intensidade',u:'mA'},{l:'Duracao',u:'min'},{l:'Modo',u:''},{l:'Grupo muscular',u:''}],
  'Duet':[{l:'Modo',u:''},{l:'Freq. US',u:'MHz'},{l:'Intens. US',u:'W'},{l:'Corrente',u:'mA'},{l:'Duracao',u:'min'},{l:'Ativo',u:''}],
  'Endermologia':[{l:'Modo',u:''},{l:'Pressao aspir.',u:'mmHg'},{l:'Vel. rolos',u:'rpm'},{l:'Duracao',u:'min'},{l:'Regiao',u:''}],
  'Limpeza de Pele':[{l:'Tecnica',u:''},{l:'Extracao',u:''},{l:'Alta freq.',u:''},{l:'Mascara',u:''}]
};

var PROTS = [
  {id:'sculpt-gold',cat:'gordura',name:'Sculpt Gold',sub:'Protocolo Premium Gordura Localizada',icon:'G',bg:'linear-gradient(135deg,#0f2035,#1c3252)',acent:'#c9a84c',desc:'Protocolo de alta performance para gordura localizada.',etapas:[{n:1,quem:'Dr. Alex',trat:'Endolaser / Lipo de Papada',detalhe:'Dissolucao cirurgica de gordura',cor:'#5b9fd4'},{n:2,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'L-Carnitina + Cafeina via US + corrente',cor:'#c9a84c'},{n:3,quem:'Viviane Costa',trat:'Criofrequencia',detalhe:'RF + frio para lipolise e drenagem',cor:'#80cbc4'},{n:4,quem:'Viviane Costa',trat:'Drenagem Linfatica',detalhe:'Ativacao linfatica pos-procedimento',cor:'#a5d6a7'},{n:5,quem:'Viviane Costa',trat:'Corrente Aussie',detalhe:'Tonificacao para potencializar resultado',cor:'#ce93d8'}],params:[{k:'Sessoes',v:'6-10'},{k:'Frequencia',v:'2x/semana'},{k:'Ativos Heccus',v:'L-Carnitina + Cafeina'},{k:'Poliaridade',v:'Positivo'},{k:'Resultado',v:'30-60 dias'}]},
  {id:'firma-premium',cat:'flacidez',name:'Firma Premium',sub:'Protocolo Premium Antiflacidez',icon:'F',bg:'linear-gradient(135deg,#0a1828,#1a2f4a)',acent:'#e2c97e',desc:'Tratamento integrado para flacidez corporal e facial.',etapas:[{n:1,quem:'Dr. Alex',trat:'HIFU',detalhe:'Acao no SMAS para lifting profundo',cor:'#80cbc4'},{n:2,quem:'Dr. Alex',trat:'RF Microagulhada',detalhe:'Remodelacao dermica fracionada',cor:'#ce93d8'},{n:3,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'Colageno + HA via US + corrente',cor:'#c9a84c'},{n:4,quem:'Viviane Costa',trat:'Criofrequencia',detalhe:'RF + frio para reafirmacao profunda',cor:'#5b9fd4'},{n:5,quem:'Viviane Costa',trat:'Corrente Aussie + Drenagem',detalhe:'Tonificacao + ativacao circulatoria',cor:'#a5d6a7'}],params:[{k:'Sessoes',v:'8-12'},{k:'Frequencia',v:'1-2x/semana'},{k:'Ativos Heccus',v:'Colageno + Escina'},{k:'Poliaridade',v:'Negativo'},{k:'Resultado',v:'45-90 dias'}]},
  {id:'detox-celular',cat:'celulite',name:'Detox Celular',sub:'Protocolo Premium Anticelulite',icon:'D',bg:'linear-gradient(135deg,#071420,#0e2030)',acent:'#80cbc4',desc:'Protocolo profundo para celulite em todos os graus.',etapas:[{n:1,quem:'Dr. Alex',trat:'Enzimas',detalhe:'Quebra do septo fibroso celulitico',cor:'#ffcc80'},{n:2,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'Aminofilina + Cafeina para lipolise nodular',cor:'#c9a84c'},{n:3,quem:'Viviane Costa',trat:'Drenagem Linfatica',detalhe:'Remocao de toxinas e edema',cor:'#a5d6a7'},{n:4,quem:'Viviane Costa',trat:'Criofrequencia',detalhe:'Reafirmacao e estimulo circulatorio',cor:'#5b9fd4'},{n:5,quem:'Viviane Costa',trat:'Corrente Aussie',detalhe:'Tonificacao e potencializacao',cor:'#ce93d8'}],params:[{k:'Sessoes',v:'10-15'},{k:'Frequencia',v:'2x/semana'},{k:'Ativos Heccus',v:'Aminofilina + Cafeina'},{k:'Poliaridade',v:'Positivo + Negativo'},{k:'Resultado',v:'30-45 dias'}]},
  {id:'revive-face',cat:'rejuvenescimento',name:'Revive Face',sub:'Protocolo Premium Rejuvenescimento',icon:'R',bg:'linear-gradient(135deg,#0c1a2e,#182d4a)',acent:'#9b7fd4',desc:'Protocolo facial completo para rejuvenescimento.',etapas:[{n:1,quem:'Dr. Alex',trat:'Botox',detalhe:'Relaxamento de rugas dinamicas',cor:'#64b5f6'},{n:2,quem:'Dr. Alex',trat:'RF Microagulhada',detalhe:'Estimulacao de colageno dermico',cor:'#ce93d8'},{n:3,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'Colageno + HA via corrente polarizada',cor:'#c9a84c'},{n:4,quem:'Viviane Costa',trat:'Drenagem Linfatica',detalhe:'Reducao de edema e tonificacao facial',cor:'#a5d6a7'},{n:5,quem:'Viviane Costa',trat:'Corrente Aussie',detalhe:'Tonificacao e lifting natural',cor:'#9b7fd4'}],params:[{k:'Sessoes',v:'6-8'},{k:'Frequencia',v:'1x/semana'},{k:'Ativos Heccus',v:'Colageno + Acido Hialuronico'},{k:'Poliaridade',v:'Negativo'},{k:'Resultado',v:'30-60 dias'}]},
  {id:'ultra-slim',cat:'gordura',name:'Ultra Slim',sub:'Protocolo Reducao Intensiva',icon:'U',bg:'linear-gradient(135deg,#0a1828,#162840)',acent:'#ffcc80',desc:'Protocolo intensivo para gordura resistente.',etapas:[{n:1,quem:'Dr. Alex',trat:'Hidrolipoclasia',detalhe:'Infiltracao hipotonica + ultrassom',cor:'#90caf9'},{n:2,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'L-Carnitina 1000mg via sonoionophorese',cor:'#c9a84c'},{n:3,quem:'Viviane Costa',trat:'Drenagem Linfatica',detalhe:'Eliminacao do volume pos-hidrolipoclasia',cor:'#a5d6a7'},{n:4,quem:'Viviane Costa',trat:'Corrente Aussie',detalhe:'Tonificacao pos-procedimento',cor:'#ce93d8'}],params:[{k:'Sessoes',v:'4-6'},{k:'Frequencia',v:'1-2x/semana'},{k:'Ativos Heccus',v:'L-Carnitina 1000mg'},{k:'Poliaridade',v:'Positivo'},{k:'Resultado',v:'21-45 dias'}]},
  {id:'neuro-lift',cat:'flacidez',name:'Neuro Lift',sub:'Lifting Sem Bisturi',icon:'N',bg:'linear-gradient(135deg,#0d1f35,#1a2f48)',acent:'#ce93d8',desc:'Lifting nao invasivo para rosto e pescoco.',etapas:[{n:1,quem:'Dr. Alex',trat:'HIFU',detalhe:'Contracao do SMAS para lifting',cor:'#80cbc4'},{n:2,quem:'Viviane Costa',trat:'Corrente Aussie',detalhe:'Reabilitacao neuromuscular',cor:'#ce93d8'},{n:3,quem:'Viviane Costa',trat:'Heccus Turbo',detalhe:'Escina + Centella para firmeza',cor:'#c9a84c'},{n:4,quem:'Viviane Costa',trat:'Drenagem Linfatica',detalhe:'Definir contorno facial',cor:'#a5d6a7'}],params:[{k:'Sessoes',v:'6-10'},{k:'Frequencia',v:'1x/semana'},{k:'Ativos Heccus',v:'Escina + Centella'},{k:'Poliaridade',v:'Negativo'},{k:'Resultado',v:'45-60 dias'}]}
];

var REGS = ['Cintura','Abdomen','Quadril','Coxa D','Coxa E','Braco D','Braco E','Gluteo'];
var ANGS = ['Frontal','Lateral D','Lateral E','Costas','Detalhe 1','Detalhe 2'];
var scores = [0,0,0,0];
var obsN = 0;
var nMedCols = 3;
var alertMap = {};
var pacKey = null;
var _cachedData = {};
var _db = null;
var _auth = null;

// =============================================
// FIREBASE — carregamento seguro e sequencial
// =============================================
function loadScript(src, cb, errCb) {
  var s = document.createElement('script');
  s.src = src;
  s.onload = cb;
  s.onerror = errCb || function() {
    document.getElementById('lista-cont').innerHTML =
      '<div style="color:#fca5a5;padding:24px;text-align:center">Erro ao carregar Firebase. Verifique sua conexao com a internet.</div>';
  };
  document.head.appendChild(s);
}

function initFirebase() {
  try {
  var cfg = {
    apiKey: "AIzaSyDsXQfnRYMY7joPGgXkIk0JCrw0BWlYglY",
    authDomain: "dr-alex-martinelli.firebaseapp.com",
    databaseURL: "https://dr-alex-martinelli-default-rtdb.firebaseio.com",
    projectId: "dr-alex-martinelli",
    storageBucket: "dr-alex-martinelli.firebasestorage.app",
    messagingSenderId: "584949990085",
    appId: "1:584949990085:web:3059e50874a113641fa6ac"
  };
  if (!firebase.apps.length) firebase.initializeApp(cfg);
  _db = firebase.database();
  _auth = firebase.auth();
  console.log('Firebase iniciado com sucesso!');
  } catch(e) {
    console.error('Erro ao iniciar Firebase:', e);
    document.getElementById('lista-cont').innerHTML =
      '<div style="color:#fca5a5;padding:24px;text-align:center">Erro Firebase: ' + e.message + '</div>';
  }
}

// =============================================
// DB — Firebase Realtime Database
// =============================================
var DB = {
  // Salva IMEDIATAMENTE no localStorage e sincroniza com Firebase em background
  _lsKey: 'intelectus_pac',
  _lsGet: function() { try { return JSON.parse(localStorage.getItem(this._lsKey)||'{}'); } catch(e) { return {}; } },
  _lsSet: function(key, val) { var d = this._lsGet(); d[key] = val; localStorage.setItem(this._lsKey, JSON.stringify(d)); },
  _lsDel: function(key) { var d = this._lsGet(); delete d[key]; localStorage.setItem(this._lsKey, JSON.stringify(d)); },

  listar: function(cb) {
    // Retorna localStorage imediatamente
    var local = this._lsGet();
    var lista = Object.keys(local).map(function(k) { return {key: k, data: local[k]}; });
    cb(lista);
    // Sincroniza com Firebase em background se disponivel
    if (_db) {
      _db.ref('clientes').once('value', function(snap) {
        var fireLista = [];
        snap.forEach(function(c) { fireLista.push({key: c.key, data: c.val()}); });
        if (fireLista.length > 0) {
          // Merge Firebase into localStorage
          var merged = DB._lsGet();
          fireLista.forEach(function(item) { merged[item.key] = item.data; });
          localStorage.setItem(DB._lsKey, JSON.stringify(merged));
        }
      });
    }
  },

  salvar: function(key, val, cb) {
    // Salva IMEDIATAMENTE no localStorage
    this._lsSet(key, val);
    if (cb) cb(true); // Sucesso instantaneo!
    // Sincroniza com Firebase em background
    if (_db) {
      _db.ref('clientes/' + key).set(val, function(err) {
        if (err) console.warn('Firebase sync error:', err);
      });
    }
  },

  carregar: function(key, cb) {
    // Carrega do localStorage imediatamente
    var local = this._lsGet();
    if (local[key]) { cb(local[key]); }
    else if (_db) {
      // Tenta Firebase se nao tiver local
      _db.ref('clientes/' + key).once('value', function(snap) {
        var d = snap.val();
        if (d) { DB._lsSet(key, d); }
        cb(d);
      });
    } else { cb(null); }
  },

  deletar: function(key, cb) {
    this._lsDel(key);
    if (cb) cb(true);
    if (_db) { _db.ref('clientes/' + key).remove(); }
  }
};

// =============================================
// TELAS
// =============================================
function mostrarLista() {
  document.getElementById('tela-lista').style.display = 'block';
  document.getElementById('tela-ficha').style.display = 'none';
  document.getElementById('btn-back').style.display = 'none';
  document.getElementById('btn-salvar').style.display = 'none';
  renderLista();
}
function mostrarFicha() {
  document.getElementById('tela-lista').style.display = 'none';
  document.getElementById('tela-ficha').style.display = 'block';
  document.getElementById('btn-back').style.display = 'inline-block';
  document.getElementById('btn-salvar').style.display = 'inline-block';
}
function voltarLista() {
  if (confirm('Voltar para a lista? Salve antes para nao perder dados.')) mostrarLista();
}

// =============================================
// LISTA
// =============================================
function renderLista(filtro) {
  filtro = filtro || '';
  document.getElementById('lista-cont').innerHTML = '<div style="text-align:center;padding:30px;color:var(--silver)">Carregando...</div>';
  DB.listar(function(lista) {
    lista.sort(function(a,b) { return (a.data.nome||'').localeCompare(b.data.nome||''); });
    var f = filtro.toLowerCase();
    var vis = f ? lista.filter(function(c) { return (c.data.nome||'').toLowerCase().indexOf(f) >= 0; }) : lista;
    document.getElementById('lsub').textContent = lista.length + ' paciente' + (lista.length !== 1 ? 's' : '') + ' cadastrado' + (lista.length !== 1 ? 's' : '');
    var cont = document.getElementById('lista-cont');
    if (!vis.length) {
      cont.innerHTML = '<div class="lvazio"><div style="font-size:2.5rem;margin-bottom:10px">+</div><div style="font-family:Cormorant Garamond,serif;font-size:1.25rem;color:var(--white);margin-bottom:5px">' + (f ? 'Nenhum resultado' : 'Nenhum paciente ainda') + '</div><p style="font-size:.7rem">' + (f ? 'Tente outro nome.' : 'Clique em Novo Paciente para comecar.') + '</p></div>';
      return;
    }
    var html = '';
    vis.forEach(function(c) {
      var nome = c.data.nome || 'Sem nome';
      var p = nome.trim().split(' ');
      var av = (p.length >= 2 ? p[0][0] + p[p.length-1][0] : p[0][0]).toUpperCase();
      var ini = c.data.inicio ? new Date(c.data.inicio + 'T12:00:00').toLocaleDateString('pt-BR') : '';
      html += '<div class="cc" data-key="' + c.key + '">' +
        '<div class="cc-av">' + av + '</div>' +
        '<div class="cc-info"><div class="cc-nome">' + nome + '</div>' +
        '<div class="cc-meta">' + (c.data.tel||'') + (ini ? ' - Desde ' + ini : '') + '</div></div>' +
        '<button class="cc-del" data-key="' + c.key + '" data-nome="' + nome + '">X</button>' +
        '<div class="cc-arr">></div></div>';
    });
    cont.innerHTML = html;
    cont.querySelectorAll('.cc').forEach(function(el) {
      el.addEventListener('click', function(e) {
        if (e.target.classList.contains('cc-del')) return;
        abrirPaciente(el.dataset.key);
      });
    });
    cont.querySelectorAll('.cc-del').forEach(function(btn) {
      btn.addEventListener('click', function(e) {
        e.stopPropagation();
        deletarPac(btn.dataset.key, btn.dataset.nome);
      });
    });
  });
}
function filtrarLista(v) { renderLista(v); }
function deletarPac(key, nome) {
  if (!confirm('Remover "' + nome + '" permanentemente?')) return;
  DB.deletar(key, function(ok) {
    if (ok) { toast('Removido: ' + nome); renderLista(); }
    else toast('Erro ao remover', 'err');
  });
}
function novoPaciente() {
  pacKey = 'p' + Date.now();
  _cachedData = {sessoes:[], pagamentos:[], receitas:[]};
  resetar();
  mostrarFicha();
  aba('dados', document.querySelector('.tab'));
}
function abrirPaciente(key) {
  pacKey = key;
  _cachedData = {sessoes:[], pagamentos:[], receitas:[]};
  resetar();
  mostrarFicha();
  document.getElementById('hn').textContent = 'Carregando...';
  DB.carregar(key, function(d) {
    if (d) {
      _cachedData = d;
      _cachedData.sessoes = _cachedData.sessoes || [];
      _cachedData.pagamentos = _cachedData.pagamentos || [];
      _cachedData.receitas = _cachedData.receitas || [];
      carregarDados(d);
    }
    aba('dados', document.querySelector('.tab'));
  });
}
function salvarPaciente() {
  var nome = document.getElementById('nome').value.trim();
  if (!nome) { toast('Informe o nome do paciente', 'err'); return; }
  if (!pacKey) { pacKey = 'p' + Date.now(); }
  var btn = document.getElementById('btn-salvar');
  btn.textContent = 'Salvando...'; btn.disabled = true;
  var dados = coletarDados();
  DB.salvar(pacKey, dados, function(ok) {
    btn.textContent = 'Salvar'; btn.disabled = false;
    if (ok) { _cachedData = JSON.parse(JSON.stringify(dados)); toast('Salvo: ' + nome); }
    else { toast('Erro ao salvar!', 'err'); }
  });
}

// =============================================
// BUSCA RAPIDA
// =============================================
function buscaRap(v) {
  var res = document.getElementById('brap-res');
  if (!v || v.length < 2) { res.style.display = 'none'; return; }
  res.style.display = 'block';
  res.innerHTML = '<div style="padding:10px 14px;color:var(--silver);font-size:.74rem">Buscando...</div>';
  DB.listar(function(lista) {
    var enc = lista.filter(function(c) { return (c.data.nome||'').toLowerCase().indexOf(v.toLowerCase()) >= 0; });
    if (!enc.length) { res.innerHTML = '<div style="padding:10px 14px;color:var(--silver);font-size:.74rem">Nenhum resultado</div>'; return; }
    var html = '';
    enc.forEach(function(c) {
      var nome = c.data.nome || 'Sem nome';
      var p = nome.trim().split(' ');
      var av = (p.length >= 2 ? p[0][0] + p[p.length-1][0] : p[0][0]).toUpperCase();
      html += '<div style="display:flex;align-items:center;gap:11px;padding:9px 14px;cursor:pointer;border-bottom:1px solid rgba(201,168,76,.07)" data-key="' + c.key + '">' +
        '<div class="cc-av" style="width:34px;height:34px;font-size:.78rem">' + av + '</div>' +
        '<div><div style="font-size:.8rem;font-weight:600;color:var(--white)">' + nome + '</div>' +
        '<div style="font-size:.63rem;color:var(--silver)">' + (c.data.tel||'') + '</div></div>' +
        '<div style="margin-left:auto;color:var(--gold);font-size:.63rem;font-weight:700">Abrir</div></div>';
    });
    res.innerHTML = html;
    res.querySelectorAll('[data-key]').forEach(function(el) {
      el.addEventListener('click', function() {
        document.getElementById('brap').value = '';
        res.style.display = 'none';
        abrirPaciente(el.dataset.key);
      });
    });
  });
}

// =============================================
// HERO / IMC / PROG
// =============================================
function atualizarHero() {
  var n = document.getElementById('nome').value;
  if (n) {
    document.getElementById('hn').textContent = n;
    var p = n.trim().split(' ');
    document.getElementById('av').textContent = (p.length >= 2 ? p[0][0] + p[p.length-1][0] : p[0][0]).toUpperCase();
  } else {
    document.getElementById('hn').textContent = 'Novo Paciente';
    document.getElementById('av').textContent = '?';
  }
  var nasc = document.getElementById('nasc').value;
  if (nasc) {
    var h = new Date(), dn = new Date(nasc + 'T12:00:00');
    var id = h.getFullYear() - dn.getFullYear();
    if (h.getMonth() - dn.getMonth() < 0 || (h.getMonth() - dn.getMonth() === 0 && h.getDate() < dn.getDate())) id--;
    document.getElementById('idade').value = id;
    document.getElementById('hm').textContent = id + ' anos - Paciente ativo';
  }
  prog();
}
function calcImc() {
  var p = parseFloat(document.getElementById('peso').value);
  var a = parseFloat(document.getElementById('alt').value) / 100;
  if (p && a) document.getElementById('imc').value = (p / (a*a)).toFixed(1);
}
function prog() {
  var ids = ['nome','tel','inicio','obj','peso'];
  var n = 0;
  ids.forEach(function(id) { var el = document.getElementById(id); if (el && el.value) n++; });
  document.getElementById('pct').textContent = Math.round(n / ids.length * 100) + '%';
}
function alerta(el, msg, tipo) {
  el.classList.toggle('on');
  var key = msg.substring(0, 15);
  if (el.classList.contains('on')) alertMap[key] = {msg: msg, tipo: tipo};
  else delete alertMap[key];
  document.getElementById('alertas').innerHTML = Object.values(alertMap).map(function(v) {
    return '<div class="al al-' + v.tipo + '"><span>' + (v.tipo === 'err' ? '!' : '?') + '</span><span>' + v.msg + '</span></div>';
  }).join('');
}
function aba(id, btn) {
  document.querySelectorAll('.panel').forEach(function(p) { p.classList.remove('on'); });
  document.querySelectorAll('.tab').forEach(function(b) { b.classList.remove('on'); });
  document.getElementById('p-' + id).classList.add('on');
  btn.classList.add('on');
  if (id === 'evolucao') { renderEvolucao(); renderKpisEvol(); }
  if (id === 'graficos') renderGraficos();
  if (id === 'protocolos') renderProts('todos');
  if (id === 'comparativo') renderComparativoInit();
  if (id === 'score') renderScore();
  if (id === 'agenda') { preencherProcsAgenda(); renderAgenda(); }
  if (id === 'faturamento') renderFinSumario(_cachedData.pagamentos || []);
  if (id === 'receituario') renderRxList();
}
function togCard(h) { h.nextElementSibling.classList.toggle('hide'); }

// =============================================
// COLETA / CARGA
// =============================================
function G(id) { var el = document.getElementById(id); return el ? el.value : ''; }
function coletarDados() {
  var medidas = [];
  REGS.forEach(function(r, i) {
    var row = {reg: r};
    for (var c = 0; c <= nMedCols; c++) { var el = document.getElementById('m' + i + '_' + c); row['c' + c] = el ? el.value : ''; }
    medidas.push(row);
  });
  var obsItems = [];
  document.querySelectorAll('#tl .tli').forEach(function(it) {
    var dt = it.querySelector('.tldt'); var tx = it.querySelector('.tltx');
    if (dt && tx && tx.textContent.indexOf('aparecerao') < 0) obsItems.push({date: dt.textContent, text: tx.textContent});
  });
  var saude = []; document.querySelectorAll('#saude-tog .tog.on').forEach(function(t) { saude.push(t.textContent); });
  return {
    nome: G('nome'), nasc: G('nasc'), tel: G('tel'), email: G('email'), cpf: G('cpf'),
    prof: G('prof'), orig: G('orig'), inicio: G('inicio'), medico: G('medico'),
    peso: G('peso'), alt: G('alt'), gord: G('gord'), obj: G('obj'),
    meds: G('meds'), alerg: G('alerg'), ciru: G('ciru'), tratAnt: G('trat-ant'),
    atv: G('atv'), alim: G('alim'), prox: G('prox-sess'), freq: G('freq'), orient: G('orient'),
    scores: scores.slice(), medidas: medidas, nMedCols: nMedCols,
    obsItems: obsItems, saude: saude,
    sessoes: _cachedData.sessoes || [],
    pagamentos: _cachedData.pagamentos || [],
    receitas: _cachedData.receitas || [],
    salvoEm: new Date().toISOString()
  };
}
function S(id, v) { var el = document.getElementById(id); if (el && v != null) el.value = v; }
function carregarDados(d) {
  S('nome',d.nome); S('nasc',d.nasc); S('tel',d.tel); S('email',d.email); S('cpf',d.cpf);
  S('prof',d.prof); S('orig',d.orig); S('inicio',d.inicio); S('medico',d.medico);
  S('peso',d.peso); S('alt',d.alt); S('gord',d.gord); S('obj',d.obj);
  S('meds',d.meds); S('alerg',d.alerg); S('ciru',d.ciru); S('trat-ant',d.tratAnt);
  S('atv',d.atv); S('alim',d.alim); S('prox-sess',d.prox); S('freq',d.freq); S('orient',d.orient);
  if (d.scores) d.scores.forEach(function(v, i) { scores[i] = v; document.querySelectorAll('#sc' + i + ' .star').forEach(function(s, j) { s.classList.toggle('on', j < v); }); });
  if (d.saude) document.querySelectorAll('#saude-tog .tog').forEach(function(t) { t.classList.toggle('on', (d.saude||[]).indexOf(t.textContent) >= 0); });
  if (d.medidas && d.nMedCols) {
    nMedCols = d.nMedCols;
    var head = document.querySelector('#med-t thead tr');
    head.innerHTML = '<th>Regiao</th><th>Inicial</th>';
    for (var c = 1; c <= nMedCols; c++) head.innerHTML += '<th>Sessao ' + c + '</th>';
    head.innerHTML += '<th>Total</th>';
    renderMed(d.medidas);
  }
  if (d.obsItems && d.obsItems.length) {
    document.getElementById('tl').innerHTML = d.obsItems.map(function(it) {
      return '<div class="tli"><div class="tld"></div><div class="tldt">' + it.date + '</div><div class="tltx">' + it.text + '</div></div>';
    }).join('');
    obsN = d.obsItems.length;
  }
  renderTratamentos(d.sessoes || []);
  renderPagamentos(d.pagamentos || []);
  renderFinSumario(d.pagamentos || []);
  renderRxList();
  atualizarHero(); calcImc(); prog();
}
function resetar() {
  scores = [0,0,0,0]; obsN = 0; nMedCols = 3; alertMap = {};
  document.querySelectorAll('#tela-ficha input:not([readonly]),#tela-ficha select,#tela-ficha textarea').forEach(function(el) { el.value = ''; });
  document.getElementById('imc').value = '';
  document.querySelectorAll('#tela-ficha .tog').forEach(function(t) { t.classList.remove('on'); });
  document.getElementById('alertas').innerHTML = '';
  for (var i = 0; i < 4; i++) document.querySelectorAll('#sc' + i + ' .star').forEach(function(s) { s.classList.remove('on'); });
  document.getElementById('tl').innerHTML = '<div class="tli"><div class="tld"></div><div class="tldt">Aguardando</div><div class="tltx" style="font-style:italic">As observacoes aparecerao aqui.</div></div>';
  document.getElementById('pag-list').innerHTML = '';
  document.getElementById('pag-empty').style.display = 'block';
  document.getElementById('fsum').innerHTML = '';
  document.getElementById('rx-list').innerHTML = '<div style="text-align:center;padding:35px;color:var(--silver);font-size:.78rem">Nenhuma receita emitida ainda.</div>';
  document.getElementById('av').textContent = '?';
  document.getElementById('hn').textContent = 'Novo Paciente';
  document.getElementById('hm').textContent = 'Preencha os dados abaixo';
  document.getElementById('pct').textContent = '0%';
  var head = document.querySelector('#med-t thead tr');
  head.innerHTML = '<th>Regiao</th><th>Inicial</th><th>Sessao 1</th><th>Sessao 2</th><th>Sessao 3</th><th>Total</th>';
  renderMed(); renderFotos();
  renderTratamentos([]);
}

// =============================================
// MEDIDAS
// =============================================
function renderMed(saved) {
  var tb = document.getElementById('med-body'); tb.innerHTML = '';
  REGS.forEach(function(reg, i) {
    var tr = document.createElement('tr');
    var h = '<td style="font-weight:600;color:var(--white);font-size:.78rem;white-space:nowrap">' + reg + '</td>';
    for (var c = 0; c <= nMedCols; c++) { var v = saved ? saved[i]['c' + c] : ''; h += '<td><input type="number" step="0.1" placeholder="0.0" id="m' + i + '_' + c + '" value="' + (v||'') + '" oninput="delta(' + i + ')"></td>'; }
    h += '<td id="dt' + i + '" class="d-n">-</td>';
    tr.innerHTML = h; tb.appendChild(tr);
    if (saved) delta(i);
  });
  graf();
}
function delta(i) {
  var ini = parseFloat((document.getElementById('m' + i + '_0')||{}).value) || 0;
  var ult = 0;
  for (var c = nMedCols; c >= 1; c--) { var el = document.getElementById('m' + i + '_' + c); var v = el ? parseFloat(el.value) : NaN; if (!isNaN(v) && v > 0) { ult = v; break; } }
  var dt = document.getElementById('dt' + i);
  if (ini > 0 && ult > 0) { var dv = +(ini - ult).toFixed(1); dt.className = dv > 0 ? 'd-ok' : dv < 0 ? 'd-err' : 'd-n'; dt.textContent = dv > 0 ? '-' + dv + 'cm' : dv < 0 ? '+' + Math.abs(dv) + 'cm' : '0cm'; }
  else { dt.className = 'd-n'; dt.textContent = '-'; }
  graf();
}
function addColMed() {
  nMedCols++;
  var head = document.querySelector('#med-t thead tr');
  var th = document.createElement('th'); th.textContent = 'Sessao ' + nMedCols; head.insertBefore(th, head.lastElementChild);
  document.querySelectorAll('#med-body tr').forEach(function(row, i) {
    var td = document.createElement('td'); td.innerHTML = '<input type="number" step="0.1" placeholder="0.0" id="m' + i + '_' + nMedCols + '" oninput="delta(' + i + ')">'; row.insertBefore(td, row.lastElementChild);
  });
}
function graf() {
  var g = document.getElementById('graf'); g.innerHTML = '';
  REGS.forEach(function(r, i) {
    var ini = parseFloat((document.getElementById('m' + i + '_0')||{}).value) || 0;
    var ult = 0;
    for (var c = nMedCols; c >= 1; c--) { var el = document.getElementById('m' + i + '_' + c); var v = el ? parseFloat(el.value) : NaN; if (!isNaN(v) && v > 0) { ult = v; break; } }
    var diff = ini > 0 && ult > 0 ? Math.max(0, ini - ult) : 0;
    var h = Math.min(diff / 10 * 80, 80);
    g.innerHTML += '<div class="bw"><div class="bv">' + (diff > 0 ? diff.toFixed(1) : '-') + '</div><div class="bar" style="height:' + h + 'px;min-height:' + (diff > 0 ? 3 : 0) + 'px"></div><div class="bl">' + r.substring(0, 4) + '</div></div>';
  });
}

// =============================================
// SESSOES
// =============================================
function abrirModalSessao(tratPresel) {
  document.getElementById('sess-trat').value = '';
  document.getElementById('sess-data').value = new Date().toISOString().split('T')[0];
  document.getElementById('sess-num').value = '';
  document.getElementById('sess-prox').value = '';
  document.getElementById('sess-reac').value = '';
  document.getElementById('sess-res').value = '';
  document.getElementById('sess-obs').value = '';
  document.getElementById('modal-params').innerHTML = '';
  var alexTrats = Object.keys(TRAT_DEFS).filter(function(t) { return TRAT_PROF[t] === 'Dr. Alex Martinelli'; });
  var viviTrats = Object.keys(TRAT_DEFS).filter(function(t) { return TRAT_PROF[t] === 'Viviane Costa'; });
  var html = '<div class="sec-lbl sec-alex">Dr. Alex Martinelli</div>';
  alexTrats.forEach(function(t) {
    var cor = TRAT_CORES[t] || '#c9a84c';
    html += '<div class="tpick" data-trat="' + t + '">' +
      '<div class="tpick-ico" style="font-size:1.6rem;margin-bottom:5px">' + (TRAT_ICONS[t]||t.substring(0,2)) + '</div>' +
      '<div class="tpick-lbl">' + t + '</div>' +
      '<span class="tpick-who who-alex">Alex</span></div>';
  });
  html += '<div class="sec-lbl sec-vivi">Viviane Costa</div>';
  viviTrats.forEach(function(t) {
    var cor = TRAT_CORES[t] || '#c9a84c';
    html += '<div class="tpick" data-trat="' + t + '">' +
      '<div class="tpick-ico" style="font-size:1.6rem;margin-bottom:5px">' + (TRAT_ICONS[t]||t.substring(0,2)) + '</div>' +
      '<div class="tpick-lbl">' + t + '</div>' +
      '<span class="tpick-who who-vivi">Viviane</span></div>';
  });
  var grid = document.getElementById('tpick-grid');
  grid.innerHTML = html;
  grid.querySelectorAll('.tpick').forEach(function(el) {
    el.addEventListener('click', function() {
      grid.querySelectorAll('.tpick').forEach(function(e) { e.classList.remove('on'); });
      el.classList.add('on');
      document.getElementById('sess-trat').value = el.dataset.trat;
      renderParamsModal(el.dataset.trat);
      var sessoes = _cachedData.sessoes || [];
      var nSess = sessoes.filter(function(s) { return s.trat === el.dataset.trat; }).length + 1;
      document.getElementById('sess-num').value = nSess;
    });
  });
  if (tratPresel) {
    var el = grid.querySelector('[data-trat="' + tratPresel + '"]');
    if (el) el.click();
  }
  document.getElementById('ov-sess').classList.add('open');
}
function renderParamsModal(trat) {
  var params = TRAT_DEFS[trat] || [];
  document.getElementById('modal-params').innerHTML = params.map(function(p, i) {
    return '<div style="background:var(--n4);border:1.5px solid var(--bd);border-radius:7px;padding:8px 10px">' +
      '<div style="font-size:.52rem;letter-spacing:.1em;text-transform:uppercase;color:var(--silver);font-weight:700;margin-bottom:3px">' + p.l + '</div>' +
      '<input type="text" placeholder="-" id="mp' + i + '" style="width:100%;border:none;background:none;font-family:Outfit,sans-serif;font-size:.82rem;font-weight:600;color:var(--g2);padding:0;outline:none">' +
      '<div style="font-size:.52rem;color:var(--silver);margin-top:1px">' + p.u + '</div></div>';
  }).join('');
}
function salvarSessao() {
  var trat = document.getElementById('sess-trat').value;
  if (!trat) { toast('Selecione o tratamento', 'err'); return; }
  if (!pacKey) { toast('Abra um paciente primeiro', 'err'); return; }
  var btnSess = document.querySelector('#ov-sess .btn-g');
  if (btnSess) { btnSess.textContent = 'Salvando...'; btnSess.disabled = true; }
  var params = TRAT_DEFS[trat] || [];
  var pVals = {};
  params.forEach(function(p, i) {
    var el = document.getElementById('mp' + i);
    pVals[p.l] = el ? el.value : '';
  });
  var sessao = {
    id: 's' + Date.now(),
    trat: trat,
    data: document.getElementById('sess-data').value,
    num: parseInt(document.getElementById('sess-num').value) || 1,
    prox: document.getElementById('sess-prox').value,
    reac: document.getElementById('sess-reac').value,
    res: document.getElementById('sess-res').value,
    obs: document.getElementById('sess-obs').value,
    params: pVals
  };
  if (!_cachedData) _cachedData = {};
  _cachedData.sessoes = _cachedData.sessoes || [];
  _cachedData.sessoes.push(sessao);
  var dados = coletarDados();
  DB.salvar(pacKey, dados, function(ok) {
    if (btnSess) { btnSess.textContent = 'Salvar Sessao'; btnSess.disabled = false; }
    if (ok) {
      fechaModal('ov-sess');
      renderTratamentos(_cachedData.sessoes);
      toast('Sessao de ' + trat + ' registrada!');
    } else {
      _cachedData.sessoes.pop();
      toast('Erro ao salvar sessao!', 'err');
    }
  });
}
function renderTratamentos(sessoes) {
  var cont = document.getElementById('trats-cont');
  if (!sessoes || !sessoes.length) {
    cont.innerHTML = '<div style="text-align:center;padding:40px;color:var(--silver)"><div style="font-size:2rem;margin-bottom:8px">+</div><div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white);margin-bottom:4px">Nenhuma sessao registrada</div><div style="font-size:.72rem">Clique em Registrar Sessao para comecar.</div></div>';
    return;
  }
  var grupos = {};
  sessoes.forEach(function(s) { if (!grupos[s.trat]) grupos[s.trat] = []; grupos[s.trat].push(s); });
  Object.keys(grupos).forEach(function(t) { grupos[t].sort(function(a,b) { return a.data.localeCompare(b.data) || a.num - b.num; }); });
  var html = '';
  Object.keys(grupos).forEach(function(trat) {
    var sess = grupos[trat];
    var ult = sess[sess.length-1];
    var ultData = ult.data ? new Date(ult.data + 'T12:00:00').toLocaleDateString('pt-BR') : '--';
    var cor = TRAT_CORES[trat] || '#c9a84c';
    var who = TRAT_PROF[trat] || '';
    var whoCor = who === 'Dr. Alex Martinelli' ? '#64b5f6' : '#c9a84c';
    var id = 'tg' + trat.replace(/\W/g,'');
    var sessHtml = sess.map(function(s) {
      var params = s.params || {};
      var paramKeys = Object.keys(params).filter(function(k) { return params[k]; });
      var paramHtml = paramKeys.length ? '<div class="pgrid">' + paramKeys.map(function(k) {
        return '<div class="pbox"><div class="plbl">' + k + '</div><div class="pval">' + params[k] + '</div></div>';
      }).join('') + '</div>' : '<div style="font-size:.7rem;color:var(--silver);font-style:italic">Sem parametros registrados.</div>';
      var dataFmt = s.data ? new Date(s.data + 'T12:00:00').toLocaleDateString('pt-BR') : '';
      var res = s.res ? s.res + ' estrela' + (parseInt(s.res) > 1 ? 's' : '') : '';
      return '<div class="sess-item">' +
        '<div class="sess-ih">' +
        '<div style="display:flex;align-items:center;gap:8px">' +
        '<span class="sess-nb">Sessao ' + s.num + '</span>' +
        '<span class="sess-dt">' + dataFmt + '</span>' +
        (res ? '<span style="font-size:.65rem;color:var(--gold)">' + res + '</span>' : '') +
        '</div>' +
        '<button data-sessid="' + s.id + '" style="background:none;border:none;cursor:pointer;color:var(--silver);font-size:.8rem;padding:2px 5px;border-radius:4px">X</button>' +
        '</div>' + paramHtml +
        (s.reac ? '<div style="font-size:.68rem;margin-top:7px;color:var(--silver)">Reacao: <span style="color:var(--white)">' + s.reac + '</span></div>' : '') +
        (s.obs ? '<div style="font-size:.74rem;line-height:1.5;margin-top:8px;padding-top:8px;border-top:1px solid rgba(201,168,76,.08);color:var(--silver)">' + s.obs + '</div>' : '') +
        (s.prox ? '<div style="font-size:.66rem;margin-top:6px;color:var(--gold)">Proxima: ' + new Date(s.prox + 'T12:00:00').toLocaleDateString('pt-BR') + '</div>' : '') +
        '</div>';
    }).join('');
    html += '<div class="trat-section">' +
      '<div class="trat-sh" id="sh' + id + '">' +
      '<div class="trat-nome"><span style="width:10px;height:10px;border-radius:50%;background:' + cor + ';display:inline-block"></span>' +
      trat +
      '<span class="trat-badge">' + sess.length + ' sess</span>' +
      '<span style="font-size:.58rem;padding:2px 8px;border-radius:8px;font-weight:700;background:rgba(0,0,0,.2);color:' + whoCor + '">' + who + '</span>' +
      '</div>' +
      '<div style="display:flex;align-items:center;gap:10px">' +
      '<span class="trat-ult">Ultima: ' + ultData + '</span>' +
      '<button data-addtrat="' + trat + '" style="background:rgba(201,168,76,.1);border:1px solid var(--bd);border-radius:6px;padding:3px 10px;cursor:pointer;color:var(--gold);font-size:.63rem;font-weight:700;font-family:Outfit,sans-serif">+ Sessao</button>' +
      '</div></div>' +
      '<div class="trat-body open" id="' + id + '">' + sessHtml + '</div>' +
      '</div>';
  });
  cont.innerHTML = html;
  cont.querySelectorAll('.trat-sh').forEach(function(el) {
    el.addEventListener('click', function(e) {
      if (e.target.dataset.addtrat || e.target.closest('[data-addtrat]')) return;
      var bodyId = el.id.replace('sh','');
      var body = document.getElementById(bodyId);
      if (body) body.classList.toggle('open');
    });
  });
  cont.querySelectorAll('[data-addtrat]').forEach(function(btn) {
    btn.addEventListener('click', function(e) { e.stopPropagation(); abrirModalSessao(btn.dataset.addtrat); });
  });
  cont.querySelectorAll('[data-sessid]').forEach(function(btn) {
    btn.addEventListener('click', function(e) { e.stopPropagation(); deletarSessao(btn.dataset.sessid); });
  });
}
function deletarSessao(sid) {
  if (!confirm('Remover esta sessao?')) return;
  _cachedData.sessoes = (_cachedData.sessoes || []).filter(function(s) { return s.id !== sid; });
  var dados = coletarDados();
  DB.salvar(pacKey, dados, function(ok) {
    if (ok) { renderTratamentos(_cachedData.sessoes); toast('Sessao removida'); }
    else toast('Erro ao remover', 'err');
  });
}

// =============================================
// EVOLUCAO
// =============================================
function renderEvolucao() {
  var sessoes = _cachedData.sessoes || [];
  var grupos = {};
  sessoes.forEach(function(s) { if (!grupos[s.trat]) grupos[s.trat] = []; grupos[s.trat].push(s); });
  var tb = document.getElementById('evol-body');
  if (!Object.keys(grupos).length) {
    tb.innerHTML = '<tr><td colspan="5" style="text-align:center;color:var(--silver);font-style:italic;padding:20px">Nenhuma sessao registrada ainda.</td></tr>';
    return;
  }
  tb.innerHTML = Object.keys(grupos).map(function(trat) {
    var sess = grupos[trat];
    sess.sort(function(a,b) { return a.data.localeCompare(b.data); });
    var ult = sess[sess.length-1];
    var ultData = ult.data ? new Date(ult.data + 'T12:00:00').toLocaleDateString('pt-BR') : '--';
    var prox = ult.prox ? new Date(ult.prox + 'T12:00:00').toLocaleDateString('pt-BR') : '--';
    var avgRes = sess.reduce(function(a,s) { return a + (parseInt(s.res)||0); }, 0) / sess.length;
    var stars = avgRes > 0 ? Math.round(avgRes) + ' estrelas' : '--';
    var cor = TRAT_CORES[trat] || '#c9a84c';
    return '<tr><td><span style="width:8px;height:8px;border-radius:50%;background:' + cor + ';display:inline-block;margin-right:6px"></span><span style="font-weight:600">' + trat + '</span></td>' +
      '<td style="text-align:center"><span style="background:rgba(201,168,76,.15);color:var(--g2);font-weight:700;padding:2px 9px;border-radius:10px;font-size:.8rem">' + sess.length + '</span></td>' +
      '<td style="color:var(--silver);font-size:.78rem">' + ultData + '</td>' +
      '<td style="color:var(--gold);font-size:.78rem">' + prox + '</td>' +
      '<td style="color:var(--gold);font-size:.78rem">' + stars + '</td></tr>';
  }).join('');
}
function renderKpisEvol() {
  var sessoes = _cachedData.sessoes || [];
  var nTrats = Object.keys(sessoes.reduce(function(a,s) { a[s.trat]=1; return a; }, {})).length;
  var avgScore = (scores[0]+scores[1]+scores[2]+scores[3]) / 4;
  var ini = document.getElementById('inicio').value;
  var dias = ini ? Math.floor((new Date() - new Date(ini + 'T12:00:00')) / 86400000) : '--';
  document.getElementById('kpis-evol').innerHTML = [
    {ic:'+',v:sessoes.length,u:'sessoes',l:'Total realizadas'},
    {ic:'T',v:nTrats,u:'tipos',l:'Tratamentos distintos'},
    {ic:'A',v:avgScore.toFixed(1),u:'/ 5',l:'Avaliacao media'},
    {ic:'D',v:dias,u:'dias',l:'Em tratamento'}
  ].map(function(k) { return '<div class="kpi"><div class="kpi-i">' + k.ic + '</div><div class="kpi-v">' + k.v + '</div><div class="kpi-u">' + k.u + '</div><div class="kpi-l">' + k.l + '</div></div>'; }).join('');
}
function setStar(gi, val) {
  scores[gi] = val;
  document.querySelectorAll('#sc' + gi + ' .star').forEach(function(s, i) { s.classList.toggle('on', i < val); });
}
function addObs() {
  var txt = document.getElementById('nova-obs').value.trim(); if (!txt) return;
  obsN++;
  var tl = document.getElementById('tl'); if (obsN === 1) tl.innerHTML = '';
  var d = new Date().toLocaleDateString('pt-BR', {day:'2-digit',month:'long',year:'numeric'});
  tl.insertAdjacentHTML('afterbegin', '<div class="tli"><div class="tld"></div><div class="tldt">' + d + '</div><div class="tltx">' + txt + '</div></div>');
  document.getElementById('nova-obs').value = '';
}

// =============================================
// FOTOS
// =============================================
function renderFotos() {
  document.getElementById('fotos-grid').innerHTML = ANGS.map(function(ang, i) {
    return '<div><div id="fs' + i + '" style="aspect-ratio:3/4;border:2px dashed var(--bd);border-radius:8px;display:flex;flex-direction:column;align-items:center;justify-content:center;cursor:pointer;background:var(--n4);position:relative;overflow:hidden;transition:border-color .2s" onclick="document.getElementById(\'fi' + i + '\').click()"><span style="font-size:1.5rem;opacity:.35">F</span><span style="font-size:.6rem;color:var(--silver);margin-top:3px">' + ang + '</span></div><input type="file" id="fi' + i + '" accept="image/*" onchange="loadFoto(' + i + ',this)"><div style="font-size:.6rem;font-weight:600;color:var(--silver);margin-top:4px;text-align:center">' + ang + '</div></div>';
  }).join('');
}
function loadFoto(i, inp) {
  if (!inp.files[0]) return;
  var r = new FileReader();
  r.onload = function(e) { var s = document.getElementById('fs' + i); s.innerHTML = '<img src="' + e.target.result + '" style="width:100%;height:100%;object-fit:cover;position:absolute;inset:0">'; };
  r.readAsDataURL(inp.files[0]);
}

// =============================================
// RECEITUARIO
// =============================================
function abrirModalRx() {
  document.getElementById('rx-pac').value = document.getElementById('nome').value || '';
  document.getElementById('rx-data').value = new Date().toISOString().split('T')[0];
  document.getElementById('rx-idade').value = document.getElementById('idade').value ? document.getElementById('idade').value + ' anos' : '';
  document.getElementById('rx-ori').value = '';
  document.getElementById('rx-meds-wrap').innerHTML = criarMedRow();
  document.getElementById('ov-rx').classList.add('open');
}
function criarMedRow() {
  return '<div style="border:1px solid var(--bd);border-radius:8px;padding:11px;margin-bottom:8px">' +
    '<div class="grid g2" style="margin-bottom:7px">' +
    '<div class="field"><label>Medicamento</label><input type="text" class="fi rx-m" placeholder="Nome + dosagem"></div>' +
    '<div class="field"><label>Posologia</label><input type="text" class="fi rx-p" placeholder="Ex: 2 caps/dia por 7 dias"></div>' +
    '</div>' +
    '<div class="field"><label>Indicacao</label><input type="text" class="fi rx-ind" placeholder="Indicacao clinica"></div>' +
    '</div>';
}
function addMedRow() { document.getElementById('rx-meds-wrap').insertAdjacentHTML('beforeend', criarMedRow()); }
function salvarRx() {
  var pac = document.getElementById('rx-pac').value.trim();
  if (!pac) { toast('Informe o nome do paciente', 'err'); return; }
  var meds = [];
  document.querySelectorAll('.rx-m').forEach(function(el, i) {
    var m = el.value.trim();
    if (m) {
      var p = document.querySelectorAll('.rx-p')[i];
      var ind = document.querySelectorAll('.rx-ind')[i];
      meds.push({m: m, p: p ? p.value : '', ind: ind ? ind.value : ''});
    }
  });
  if (!meds.length) { toast('Adicione ao menos um medicamento', 'err'); return; }
  var rx = {
    id: 'rx' + Date.now(), pac: pac,
    data: document.getElementById('rx-data').value,
    idade: document.getElementById('rx-idade').value,
    meds: meds, ori: document.getElementById('rx-ori').value
  };
  _cachedData.receitas = _cachedData.receitas || [];
  _cachedData.receitas.push(rx);
  DB.salvar(pacKey, coletarDados(), function(ok) {
    if (ok) { fechaModal('ov-rx'); renderRxList(); viewRx(rx); toast('Receita salva!'); }
    else toast('Erro ao salvar', 'err');
  });
}
var _rxCache = {};
function renderRxList() {
  var rxs = _cachedData.receitas || [];
  var cont = document.getElementById('rx-list');
  if (!rxs.length) { cont.innerHTML = '<div style="text-align:center;padding:35px;color:var(--silver);font-size:.78rem">Nenhuma receita emitida ainda.</div>'; return; }
  _rxCache = {};
  rxs.forEach(function(rx) { _rxCache[rx.id] = rx; });
  var html = '';
  rxs.slice().reverse().forEach(function(rx) {
    var dataFmt = rx.data ? new Date(rx.data + 'T12:00:00').toLocaleDateString('pt-BR') : '';
    html += '<div style="background:var(--n3);border:1px solid var(--bd);border-radius:10px;padding:13px 15px;margin-bottom:8px;display:flex;align-items:center;gap:12px">' +
      '<div style="font-size:1.3rem">R</div>' +
      '<div style="flex:1"><div style="font-size:.82rem;font-weight:700;color:var(--white)">' + rx.pac + '</div>' +
      '<div style="font-size:.7rem;color:var(--silver);margin-top:2px">' + rx.meds.map(function(m) { return m.m; }).join(', ') + '</div>' +
      '<div style="font-size:.62rem;color:var(--gold);margin-top:4px">' + dataFmt + '</div></div>' +
      '<button class="btn btn-m" style="font-size:.62rem" data-rxid="' + rx.id + '">Ver</button>' +
      '<button style="background:none;border:none;cursor:pointer;color:var(--silver);font-size:.85rem;padding:3px 6px;border-radius:5px;margin-left:4px" data-delrx="' + rx.id + '">X</button>' +
      '</div>';
  });
  cont.innerHTML = html;
  cont.querySelectorAll('[data-rxid]').forEach(function(btn) {
    btn.addEventListener('click', function() { viewRx(_rxCache[btn.dataset.rxid]); });
  });
  cont.querySelectorAll('[data-delrx]').forEach(function(btn) {
    btn.addEventListener('click', function() { deletarRx(btn.dataset.delrx); });
  });
}
function deletarRx(rid) {
  if (!confirm('Remover esta receita?')) return;
  _cachedData.receitas = (_cachedData.receitas||[]).filter(function(r) { return r.id !== rid; });
  DB.salvar(pacKey, coletarDados(), function(ok) {
    if (ok) { renderRxList(); toast('Receita removida'); }
    else toast('Erro ao remover', 'err');
  });
}
function viewRx(rx) {
  var dataFmt = rx.data ? new Date(rx.data + 'T12:00:00').toLocaleDateString('pt-BR', {day:'2-digit',month:'long',year:'numeric'}) : '';
  var medsHtml = rx.meds.map(function(m) {
    return '<div class="rx-item"><div class="rx-med">' + m.m + '</div><div class="rx-dose">' + m.p + '</div>' + (m.ind ? '<div style="font-size:.68rem;color:#888;margin-top:2px;font-style:italic">Indicacao: ' + m.ind + '</div>' : '') + '</div>';
  }).join('');
  document.getElementById('rx-preview-content').innerHTML =
    '<div class="rx-preview">' +
    '<div class="rx-h"><div class="rx-brand">Dr. Alex Martinelli</div>' +
    '<div class="rx-sub">Dermatologia - Medicina Estetica</div>' +
    '<div class="rx-crm">CRM/RJ 5273573-6</div>' +
    '<div class="rx-end">Rua Dois de Dezembro, 38 - Flamengo, Rio de Janeiro - RJ</div></div>' +
    '<div class="rx-pac"><div><strong>Paciente:</strong> ' + rx.pac + '</div><div><strong>Data:</strong> ' + dataFmt + '</div>' +
    (rx.idade ? '<div><strong>Idade:</strong> ' + rx.idade + '</div>' : '<div></div>') + '<div></div></div>' +
    '<div class="rx-body"><div class="rx-sym">Rx</div>' + medsHtml + '</div>' +
    (rx.ori ? '<div style="background:#f9f6f0;padding:10px;border-radius:7px;margin-bottom:14px;font-size:.74rem;color:#555"><strong>Orientacoes:</strong> ' + rx.ori + '</div>' : '') +
    '<div class="rx-ass"><div class="rx-ass-line">Assinatura e Carimbo</div></div>' +
    '<div class="rx-foot">Rio de Janeiro, ' + dataFmt + '</div></div>';
  document.getElementById('ov-rx-view').classList.add('open');
}

// =============================================
// FATURAMENTO
// =============================================
function abrirModalPag() {
  document.getElementById('pag-pac').value = document.getElementById('nome').value || '';
  document.getElementById('pag-data').value = new Date().toISOString().split('T')[0];
  document.getElementById('pag-proc').value = '';
  document.getElementById('pag-val').value = '';
  document.getElementById('pag-forma').value = '';
  document.getElementById('pag-status').value = 'pago';
  document.getElementById('pag-obs').value = '';
  document.getElementById('ov-pag').classList.add('open');
}
function salvarPag() {
  var pac = document.getElementById('pag-pac').value.trim();
  var proc = document.getElementById('pag-proc').value.trim();
  var val = parseFloat(document.getElementById('pag-val').value);
  if (!pac || !proc || !val) { toast('Preencha paciente, procedimento e valor', 'err'); return; }
  var pag = {
    id: 'pg' + Date.now(), pac: pac, proc: proc, val: val,
    forma: document.getElementById('pag-forma').value,
    status: document.getElementById('pag-status').value,
    data: document.getElementById('pag-data').value,
    obs: document.getElementById('pag-obs').value
  };
  _cachedData.pagamentos = _cachedData.pagamentos || [];
  _cachedData.pagamentos.push(pag);
  DB.salvar(pacKey, coletarDados(), function(ok) {
    if (ok) { fechaModal('ov-pag'); renderPagamentos(_cachedData.pagamentos); renderFinSumario(_cachedData.pagamentos); toast('Pagamento registrado'); }
    else toast('Erro ao salvar', 'err');
  });
}
function renderPagamentos(pags) {
  var cont = document.getElementById('pag-list');
  if (!pags || !pags.length) { document.getElementById('pag-empty').style.display = 'block'; cont.innerHTML = ''; return; }
  document.getElementById('pag-empty').style.display = 'none';
  var html = '';
  pags.slice().reverse().forEach(function(p) {
    var dataFmt = p.data ? new Date(p.data + 'T12:00:00').toLocaleDateString('pt-BR') : '';
    var spill = p.status === 'pago' ? 'sp-pago' : p.status === 'parcelado' ? 'sp-parc' : 'sp-pend';
    var stxt = p.status === 'pago' ? 'Pago' : p.status === 'parcelado' ? 'Parcelado' : 'Pendente';
    html += '<div class="pitem">' +
      '<div class="pico">R$</div>' +
      '<div class="pinfo"><div class="pnm">' + p.pac + ' - ' + p.proc + '</div>' +
      '<div class="ppr">' + (p.forma||'') + ' - ' + dataFmt + (p.obs ? ' - ' + p.obs : '') + '</div></div>' +
      '<div><div class="pv ' + (p.status === 'pendente' ? 'pend' : 'pago') + '">R$ ' + p.val.toFixed(2).replace('.',',') + '</div></div>' +
      '<span class="spill ' + spill + '">' + stxt + '</span>' +
      '<button data-pagid="' + p.id + '" style="background:none;border:none;cursor:pointer;color:var(--silver);font-size:.85rem;padding:3px 6px;border-radius:5px;margin-left:6px">X</button>' +
      '</div>';
  });
  cont.innerHTML = html;
  cont.querySelectorAll('[data-pagid]').forEach(function(btn) {
    btn.addEventListener('click', function() { deletarPag(btn.dataset.pagid); });
  });
}
function deletarPag(pid) {
  if (!confirm('Remover este pagamento?')) return;
  _cachedData.pagamentos = (_cachedData.pagamentos||[]).filter(function(p) { return p.id !== pid; });
  DB.salvar(pacKey, coletarDados(), function(ok) {
    if (ok) { renderPagamentos(_cachedData.pagamentos); renderFinSumario(_cachedData.pagamentos); toast('Pagamento removido'); }
    else toast('Erro ao remover', 'err');
  });
}
function renderFinSumario(pags) {
  pags = pags || _cachedData.pagamentos || [];
  var rec = 0, pen = 0, tot = 0;
  pags.forEach(function(p) { tot += p.val||0; if (p.status === 'pendente') pen += p.val||0; else rec += p.val||0; });
  function fmt(v) { return 'R$ ' + v.toFixed(2).replace('.',','); }
  document.getElementById('fsum').innerHTML =
    '<div class="fcard rec"><div class="flbl">Recebido</div><div class="fval">' + fmt(rec) + '</div></div>' +
    '<div class="fcard pen"><div class="flbl">Pendente</div><div class="fval">' + fmt(pen) + '</div></div>' +
    '<div class="fcard tot"><div class="flbl">Total</div><div class="fval">' + fmt(tot) + '</div></div>';
}

// =============================================
// GRAFICOS
// =============================================
function renderGraficos() {
  var sessoes = _cachedData.sessoes || [];
  var pags = _cachedData.pagamentos || [];
  var grupos = {};
  sessoes.forEach(function(s) { grupos[s.trat] = (grupos[s.trat]||0) + 1; });
  var totalRec = pags.filter(function(p) { return p.status !== 'pendente'; }).reduce(function(a,p) { return a + p.val; }, 0);
  document.getElementById('kpis-graf').innerHTML = [
    {ic:'+',v:sessoes.length,u:'sessoes',l:'Total'},
    {ic:'T',v:Object.keys(grupos).length,u:'tipos',l:'Tratamentos'},
    {ic:'R$',v:'R$'+Math.floor(totalRec),u:'',l:'Total recebido'},
    {ic:'P',v:pags.length,u:'pags',l:'Pagamentos'}
  ].map(function(k) { return '<div class="kpi"><div class="kpi-i">' + k.ic + '</div><div class="kpi-v">' + k.v + '</div><div class="kpi-u">' + k.u + '</div><div class="kpi-l">' + k.l + '</div></div>'; }).join('');
  var sorted = Object.keys(grupos).sort(function(a,b) { return grupos[b] - grupos[a]; }).slice(0, 8);
  var max = sorted.length ? grupos[sorted[0]] : 1;
  document.getElementById('graf-trats').innerHTML = sorted.map(function(t) {
    var cor = TRAT_CORES[t] || '#c9a84c';
    var pct = Math.round(grupos[t] / max * 100);
    return '<div>' +
      '<div style="display:flex;justify-content:space-between;font-size:.68rem;margin-bottom:3px"><span>' + t + '</span><span style="color:var(--gold);font-weight:700">' + grupos[t] + '</span></div>' +
      '<div style="height:5px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden"><div style="height:100%;width:' + pct + '%;background:' + cor + ';border-radius:3px;transition:width .6s"></div></div>' +
      '</div>';
  }).join('');
  var scoreLbls = ['Reducao medidas','Celulite','Flacidez','Satisfacao'];
  document.getElementById('graf-prog').innerHTML = scoreLbls.map(function(lbl, i) {
    var pct = Math.round(scores[i] / 5 * 100);
    return '<div>' +
      '<div style="display:flex;justify-content:space-between;font-size:.68rem;margin-bottom:3px"><span>' + lbl + '</span><span style="color:var(--gold);font-weight:700">' + scores[i] + '/5</span></div>' +
      '<div style="height:5px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden"><div style="height:100%;width:' + pct + '%;background:var(--gold);border-radius:3px;transition:width .6s"></div></div>' +
      '</div>';
  }).join('');
}

// =============================================
// PROTOCOLOS
// =============================================
function filtroProt(el, cat) {
  document.querySelectorAll('.pcat').forEach(function(b) { b.classList.remove('on'); }); el.classList.add('on'); renderProts(cat);
}
function renderProts(cat) {
  var lista = cat === 'todos' ? PROTS : PROTS.filter(function(p) { return p.cat === cat; });
  document.getElementById('prot-grid').innerHTML = lista.map(function(p) {
    return '<div class="pcard" style="' + p.bg + '" data-protid="' + p.id + '">' +
      '<div class="pbadge" style="border-bottom:1px solid rgba(255,255,255,.08)"><div><div class="pname" style="color:' + p.acent + '">' + p.name + '</div><div class="psub" style="color:rgba(255,255,255,.5)">' + p.sub + '</div></div><div class="picon">' + p.icon + '</div></div>' +
      '<div class="pbody">' + p.etapas.map(function(e) {
        return '<div class="pstep"><div class="psn" style="background:' + e.cor + ';color:var(--ink)">' + e.n + '</div><div class="pstxt"><strong>' + e.trat + '</strong><span style="font-size:.6rem;color:var(--gold)">' + e.quem + '</span> - ' + e.detalhe + '</div></div>';
      }).join('') + '</div>' +
      '<div class="pdet" id="pd-' + p.id + '"><div style="font-size:.56rem;letter-spacing:.15em;text-transform:uppercase;color:var(--gold);font-weight:700;margin-bottom:7px">PARAMETROS</div>' +
      p.params.map(function(pr) { return '<div class="ppr2"><span class="ppk">' + pr.k + '</span><span class="ppv">' + pr.v + '</span></div>'; }).join('') +
      '<p style="font-size:.7rem;color:var(--silver);margin-top:9px;line-height:1.5">' + p.desc + '</p></div></div>';
  }).join('');
  document.getElementById('prot-grid').querySelectorAll('.pcard').forEach(function(el) {
    el.addEventListener('click', function() {
      document.getElementById('pd-' + el.dataset.protid).classList.toggle('open');
    });
  });
}


// ══════════════════════════════════════════
// IA — SUGESTÃO DE PROTOCOLO
// ══════════════════════════════════════════
function rodarIA() {
  var painel = document.getElementById('ia-painel');
  var loading = document.getElementById('ia-loading');
  var result = document.getElementById('ia-result');
  var btn = document.getElementById('ia-btn');

  painel.style.display = 'block';
  loading.style.display = 'flex';
  result.className = 'ia-result';
  result.innerHTML = '';
  btn.disabled = true;
  btn.textContent = 'Analisando...';

  // Coleta dados do paciente
  var obj = (document.getElementById('obj').value || '').toLowerCase();
  var imc = parseFloat(document.getElementById('imc').value) || 0;
  var gord = parseFloat(document.getElementById('gord').value) || 0;
  var sc = scores || [0,0,0,0];
  var sessoes = _cachedData.sessoes || [];
  var saude = [];
  document.querySelectorAll('#saude-tog .tog.on').forEach(function(t) { saude.push(t.textContent.toLowerCase()); });

  // Conta sessões por tratamento
  var gruposSess = {};
  sessoes.forEach(function(s) { gruposSess[s.trat] = (gruposSess[s.trat]||0) + 1; });

  // Calcula redução total de medidas
  var totalRed = 0;
  REGS.forEach(function(r, i) {
    var elIni = document.getElementById('m'+i+'_0');
    var iniV = elIni ? parseFloat(elIni.value)||0 : 0;
    if (!iniV) return;
    for (var c = 3; c >= 1; c--) {
      var el = document.getElementById('m'+i+'_'+c);
      if (el && parseFloat(el.value)) { totalRed += Math.max(0, iniV - parseFloat(el.value)); break; }
    }
  });

  // ═══════════════════════════════════════
  // MOTOR DE PONTUAÇÃO LOCAL
  // Cada protocolo recebe pontos por critérios
  // ═══════════════════════════════════════

  // Palavras-chave de objetivo
  var kwGordura   = ['gordura','lipolise','emagrecer','barriga','flanco','culote','reduz','peso','slim','lipo'];
  var kwFlacidez  = ['flacidez','firmeza','firmar','sagging','lifting','tensionar','tonific'];
  var kwCelulite  = ['celulite','casca','laranja','fibrose','nodulo','irregularidade'];
  var kwReju      = ['rejuven','facial','rosto','manchas','rugas','expressao','olhos','pescoco'];

  function matchKw(kws) { return kws.filter(function(k){ return obj.indexOf(k)>=0; }).length; }

  var mGord  = matchKw(kwGordura);
  var mFlac  = matchKw(kwFlacidez);
  var mCelu  = matchKw(kwCelulite);
  var mReju  = matchKw(kwReju);

  // IMC: acima de 27 sugere gordura, 30+ sugere obesidade
  var imcGordura = imc >= 27 ? (imc >= 30 ? 3 : 2) : 0;
  // Gordura corporal %: acima de 28% mulher / 20% homem
  var gordScore = gord > 28 ? 2 : gord > 22 ? 1 : 0;

  // Histórico: premiamos variedade e protocolos já iniciados
  var jaFezHeccus  = (gruposSess['Heccus Turbo']||0);
  var jaFezCrio    = (gruposSess['Criofrequencia']||0);
  var jaFezDren    = (gruposSess['Drenagem Linfatica']||0);
  var jaFezHIFU    = (gruposSess['HIFU']||0);
  var jaFezRF      = (gruposSess['RF Microagulhada']||0);
  var jaFezEnzimas = (gruposSess['Enzimas']||0);
  var jaFezLipo    = (gruposSess['Lipo de Papada']||0);

  // Score de resultado atual (0-5)
  var scMed  = sc[0]; // redução medidas
  var scCelu = sc[1]; // celulite
  var scFlac = sc[2]; // flacidez
  var scSat  = sc[3]; // satisfação

  // Contraind
  var temMarcapasso = saude.indexOf('marcapasso') >= 0;
  var temTrombose   = saude.indexOf('trombose') >= 0;
  var temCardio     = saude.indexOf('cardiaco') >= 0 || saude.indexOf('cardiovascular') >= 0;
  var temEpilepsia  = saude.indexOf('epilepsia') >= 0;

  // ── PONTUAÇÃO POR PROTOCOLO ──────────────────
  var scoring = {

    'sculpt-gold': (function() {
      var pts = 0;
      pts += mGord * 20;
      pts += imcGordura * 15;
      pts += gordScore * 12;
      pts += jaFezHeccus  * 8;
      pts += jaFezCrio    * 6;
      pts += jaFezDren    * 5;
      // Bônus se medidas caindo
      if (totalRed > 5)  pts += 20;
      else if (totalRed > 2) pts += 10;
      // Penalidades
      if (temTrombose)   pts -= 30;
      if (temMarcapasso) pts -= 20;
      return Math.max(0, Math.min(pts, 100));
    })(),

    'firma-premium': (function() {
      var pts = 0;
      pts += mFlac * 22;
      pts += jaFezHIFU  * 10;
      pts += jaFezRF    * 10;
      pts += jaFezHeccus * 7;
      if (scFlac >= 3)   pts += 15;
      if (imc >= 25)     pts += 5;
      if (temMarcapasso) pts -= 40; // RF contraindicado
      if (temEpilepsia)  pts -= 20;
      return Math.max(0, Math.min(pts, 100));
    })(),

    'detox-celular': (function() {
      var pts = 0;
      pts += mCelu * 25;
      pts += jaFezEnzimas * 12;
      pts += jaFezHeccus  * 8;
      pts += jaFezDren    * 6;
      if (scCelu >= 3)   pts += 15;
      if (gordScore > 0) pts += 8;
      if (temTrombose)   pts -= 35;
      return Math.max(0, Math.min(pts, 100));
    })(),

    'revive-face': (function() {
      var pts = 0;
      pts += mReju * 25;
      pts += jaFezRF   * 10;
      pts += jaFezHIFU *  8;
      if (scFlac >= 3) pts += 10;
      if (scSat >= 4)  pts += 10;
      if (temMarcapasso) pts -= 35;
      return Math.max(0, Math.min(pts, 100));
    })(),

    'ultra-slim': (function() {
      var pts = 0;
      pts += mGord * 18;
      pts += imcGordura * 18;
      pts += gordScore  * 14;
      // Ultra Slim é para gordura resistente — premia se sculpt já foi feito
      if (jaFezHeccus >= 4) pts += 20;
      if (totalRed > 0 && totalRed < 3) pts += 15; // pouco resultado = precisa intensificar
      if (temTrombose)   pts -= 30;
      if (temMarcapasso) pts -= 15;
      return Math.max(0, Math.min(pts, 100));
    })(),

    'neuro-lift': (function() {
      var pts = 0;
      pts += mReju * 15;
      pts += mFlac * 12;
      pts += jaFezHIFU * 12;
      pts += jaFezRF   *  8;
      if (scFlac >= 4) pts += 15;
      if (temMarcapasso) pts -= 40;
      if (temEpilepsia)  pts -= 25;
      return Math.max(0, Math.min(pts, 100));
    })()
  };

  // Ordena por pontuação
  var ranked = PROTS.map(function(p) {
    return { prot: p, pts: scoring[p.id] || 0 };
  }).sort(function(a,b){ return b.pts - a.pts; });

  // Pega top 2
  var top2 = ranked.slice(0, 2);

  // Normaliza: maior vira 95%, segundo proporcional (min 45)
  var maxPts = top2[0].pts || 1;
  var match0 = Math.min(95, Math.max(50, Math.round(top2[0].pts / 100 * 95)));
  var match1 = Math.min(match0 - 8, Math.max(45, Math.round(top2[1].pts / 100 * 85)));

  // Gera justificativas dinâmicas
  function getJustificativa(p, pts) {
    var t = p.id;
    var base = p.desc;
    var extras = [];
    if (mGord > 0  && (t==='sculpt-gold'||t==='ultra-slim'))   extras.push('objetivo de redução de gordura identificado');
    if (mFlac > 0  && (t==='firma-premium'||t==='neuro-lift'))  extras.push('queixa de flacidez presente');
    if (mCelu > 0  && t==='detox-celular')                      extras.push('celulite identificada no objetivo');
    if (mReju > 0  && (t==='revive-face'||t==='neuro-lift'))    extras.push('foco em rejuvenescimento');
    if (imc >= 27  && (t==='sculpt-gold'||t==='ultra-slim'))    extras.push('IMC ' + imc.toFixed(1) + ' indica acúmulo adiposo');
    if (totalRed > 2 && t==='sculpt-gold')                      extras.push(totalRed.toFixed(1) + 'cm já reduzidos — protocolo em andamento');
    if (jaFezHeccus >= 3 && t==='ultra-slim')                   extras.push(jaFezHeccus + ' sessões de Heccus Turbo — pronto para intensificar');
    if (!extras.length) extras.push('perfil clínico compatível com este protocolo');
    return base + ' ' + extras.join('; ') + '.';
  }

  function getProxSessao(p) {
    var map = {
      'sculpt-gold':    'Heccus Turbo com L-Carnitina — principal ativo do protocolo para ativação lipolítica.',
      'firma-premium':  'Criofrequência — combina RF com frio para reafirmação profunda.',
      'detox-celular':  'Drenagem Linfática — essencial para eliminar toxinas e edema.',
      'revive-face':    'RF Microagulhada — estimulação de colágeno para rejuvenescimento dérmico.',
      'ultra-slim':     'Heccus Turbo com L-Carnitina 1000mg — dose intensiva para gordura resistente.',
      'neuro-lift':     'HIFU — contração do SMAS para lifting não invasivo profundo.'
    };
    return map[p.id] || p.etapas[0].trat;
  }

  // Alertas de contraind
  var alertas = [];
  if (temMarcapasso) alertas.push('⚠️ Marcapasso: RF Microagulhada, HIFU e Corrente Aussie são contraindicados.');
  if (temTrombose)   alertas.push('⚠️ Histórico de trombose: Drenagem Linfática requer avaliação médica prévia.');
  if (temEpilepsia)  alertas.push('⚠️ Epilepsia: evitar equipamentos com estímulo elétrico intenso.');

  var ia = {
    sugestoes: [
      { protocolo: top2[0].prot.name, match: match0, justificativa: getJustificativa(top2[0].prot, top2[0].pts), proxSessao: getProxSessao(top2[0].prot), etapas: top2[0].prot.etapas.map(function(e){return e.trat;}) },
      { protocolo: top2[1].prot.name, match: match1, justificativa: getJustificativa(top2[1].prot, top2[1].pts), proxSessao: getProxSessao(top2[1].prot), etapas: top2[1].prot.etapas.map(function(e){return e.trat;}) }
    ],
    alerta: alertas.join(' '),
    resumo: sessoes.length > 0
      ? 'Paciente com ' + sessoes.length + ' sessão(ões) — continue o protocolo para resultados consistentes.'
      : 'Novo paciente — o primeiro protocolo define a trajetória do tratamento.'
  };

  // Simula processamento (UX)
  setTimeout(function() {
    loading.style.display = 'none';
    btn.disabled = false;
    btn.textContent = '✦ Atualizar Análise';
    renderIAResult(ia);
  }, 1400);
}

function renderIAResult(ia) {
  var result = document.getElementById('ia-result');
  var cores = ['linear-gradient(135deg,rgba(201,168,76,.08),rgba(201,168,76,.03))', 'linear-gradient(135deg,rgba(45,212,191,.06),rgba(45,212,191,.02))'];
  var rankLabels = ['1ª Recomendação', '2ª Recomendação'];
  var rankCores = ['#c9a84c','#4cba85'];

  var html = '';

  // Alerta de contraindicação
  if (ia.alerta) {
    html += '<div class="ia-warn"><span>⚠️</span><span>' + ia.alerta + '</span></div>';
  }

  // Cards de protocolo
  (ia.sugestoes || []).forEach(function(s, i) {
    var prot = PROTS.find(function(p) { return p.name === s.protocolo; });
    var cor = prot ? prot.acent : rankCores[i];
    var bg = prot ? prot.bg : cores[i];
    html += '<div class="ia-prot-card" style="background:' + bg + ';border-color:' + cor + '40">';
    html += '<div class="ia-prot-rank" style="color:' + cor + '">' + rankLabels[i] + ' · ' + s.match + '% compatível</div>';
    html += '<div class="ia-prot-name" style="color:' + cor + '">' + s.protocolo + '</div>';
    html += '<div class="ia-prot-match"><div class="ia-match-bar"><div class="ia-match-fill" style="width:0%;background:linear-gradient(to right,' + cor + ',#fff8);" data-w="' + s.match + '"></div></div><div class="ia-match-pct">' + s.match + '%</div></div>';
    html += '<div class="ia-prot-why">' + s.justificativa + '</div>';
    if (s.etapas && s.etapas.length) {
      html += '<div class="ia-steps">' + s.etapas.map(function(e) { return '<span class="ia-step" style="background:' + cor + '20;color:' + cor + ';border:1px solid ' + cor + '40">' + e + '</span>'; }).join('') + '</div>';
    }
    html += '</div>';
  });

  // Próxima sessão recomendada
  if (ia.sugestoes && ia.sugestoes[0] && ia.sugestoes[0].proxSessao) {
    html += '<div class="ia-next"><strong>Próxima sessão recomendada:</strong> ' + ia.sugestoes[0].proxSessao + '</div>';
  }

  // Resumo motivacional
  if (ia.resumo) {
    html += '<div style="text-align:center;font-family:Cormorant Garamond,serif;font-style:italic;font-size:.9rem;color:rgba(201,168,76,.6);margin-top:12px;padding-top:10px;border-top:1px solid rgba(201,168,76,.1)">' + ia.resumo + '</div>';
  }

  result.innerHTML = html;
  result.className = 'ia-result show';

  // Animar barras depois de renderizar
  setTimeout(function() {
    result.querySelectorAll('.ia-match-fill').forEach(function(el) {
      el.style.width = el.dataset.w + '%';
    });
  }, 100);
}



// ══════════════════════════════════════════
// FUNCIONALIDADE 2: RELATÓRIO PDF
// ══════════════════════════════════════════
function gerarRelatorio() {
  var nome = document.getElementById('nome').value || 'Paciente';
  var ini = document.getElementById('inicio').value;
  var sessoes = _cachedData.sessoes || [];
  var pags = _cachedData.pagamentos || [];
  var sc = scores || [0,0,0,0];

  // KPIs
  var totalSess = sessoes.length;
  var nTrats = Object.keys(sessoes.reduce(function(a,s){a[s.trat]=1;return a;},{})).length;
  var totalRec = pags.filter(function(p){return p.status!=='pendente';}).reduce(function(a,p){return a+p.val;},0);
  var diasTrat = ini ? Math.floor((new Date()-new Date(ini+'T12:00:00'))/86400000) : 0;

  // Medidas
  var medidasHTML = '';
  var temMedida = false;
  REGS.forEach(function(reg, i) {
    var elIni = document.getElementById('m'+i+'_0');
    var iniV = elIni ? parseFloat(elIni.value)||0 : 0;
    if (!iniV) return;
    temMedida = true;
    var ultV = 0;
    for (var c = 3; c >= 1; c--) { var el = document.getElementById('m'+i+'_'+c); if (el && parseFloat(el.value)) { ultV = parseFloat(el.value); break; } }
    var diff = ultV ? iniV - ultV : 0;
    var pct = iniV > 0 && ultV > 0 ? Math.max(0, Math.round((1 - ultV/iniV)*100)) : 0;
    var deltaClass = diff > 0 ? 'pos' : diff < 0 ? 'neg' : 'neu';
    var deltaSign = diff > 0 ? '-' : diff < 0 ? '+' : '';
    medidasHTML += '<div class="rel-med-row">' +
      '<div class="rel-med-reg">' + reg + '</div>' +
      '<div class="rel-med-ini">' + iniV.toFixed(1) + '</div>' +
      '<div class="rel-med-bar-wrap"><div class="rel-med-bar" style="width:' + pct + '%"></div></div>' +
      '<div class="rel-med-ult">' + (ultV ? ultV.toFixed(1) : '--') + '</div>' +
      '<div class="rel-med-delta ' + deltaClass + '">' + (diff ? deltaSign + Math.abs(diff).toFixed(1) + 'cm' : '--') + '</div>' +
      '</div>';
  });

  // Sessões por tratamento
  var grupos = {};
  sessoes.forEach(function(s) {
    if (!grupos[s.trat]) grupos[s.trat] = {count:0,res:[]};
    grupos[s.trat].count++;
    if (s.res) grupos[s.trat].res.push(parseInt(s.res));
  });
  var sessoesHTML = '';
  Object.keys(grupos).forEach(function(trat) {
    var g = grupos[trat];
    var avgRes = g.res.length ? Math.round(g.res.reduce(function(a,v){return a+v;},0)/g.res.length) : 0;
    var cor = TRAT_CORES[trat] || '#c9a84c';
    var stars = avgRes ? Array(avgRes+1).join('★') + Array(6-avgRes).join('☆') : '';
    sessoesHTML += '<div class="rel-sess-row">' +
      '<div class="rel-sess-ico" style="background:' + cor + '">' + (TRAT_ICONS[trat]||trat.substring(0,2)) + '</div>' +
      '<div class="rel-sess-nome">' + trat + '</div>' +
      '<div class="rel-sess-qt">' + g.count + ' sess.</div>' +
      (stars ? '<div class="rel-stars" style="font-size:.75rem">' + stars + '</div>' : '') +
      '</div>';
  });

  // Avaliações
  var avalLabels = ['Redução de medidas','Melhora da celulite','Firmeza/flacidez','Satisfação geral'];
  var avalHTML = avalLabels.map(function(lbl, i) {
    var stars = sc[i] ? Array(sc[i]+1).join('★') + Array(6-sc[i]).join('☆') : '☆☆☆☆☆';
    return '<div class="rel-stars-row"><div class="rel-stars-lbl">' + lbl + '</div><div class="rel-stars">' + stars + '</div></div>';
  }).join('');

  var dataGerado = new Date().toLocaleDateString('pt-BR',{day:'2-digit',month:'long',year:'numeric'});
  var dataIni = ini ? new Date(ini+'T12:00:00').toLocaleDateString('pt-BR',{month:'long',year:'numeric'}) : '';

  document.getElementById('relatorio-content').innerHTML =
    '<div class="rel-preview">' +
    '<div class="rel-capa">' +
    '<div class="rel-marca">Intelectus</div>' +
    '<div class="rel-subtit">Relatório de Evolução Clínica</div>' +
    '<div class="rel-pac-nome">' + nome + '</div>' +
    (dataIni ? '<div class="rel-periodo">Em tratamento desde ' + dataIni + '</div>' : '') +
    '</div>' +
    '<div class="rel-body">' +
    '<div class="rel-section">' +
    '<div class="rel-section-title">Resumo do Tratamento</div>' +
    '<div class="rel-kpis">' +
    '<div class="rel-kpi"><div class="rel-kv">' + totalSess + '</div><div class="rel-kl">Sessões</div></div>' +
    '<div class="rel-kpi"><div class="rel-kv">' + nTrats + '</div><div class="rel-kl">Tratamentos</div></div>' +
    '<div class="rel-kpi"><div class="rel-kv">' + diasTrat + '</div><div class="rel-kl">Dias</div></div>' +
    '<div class="rel-kpi"><div class="rel-kv">' + (sc[3]||0) + '/5</div><div class="rel-kl">Satisfação</div></div>' +
    '</div></div>' +
    (temMedida ? '<div class="rel-section"><div class="rel-section-title">Evolução de Medidas</div>' +
    '<div style="display:flex;font-size:.6rem;color:#888;padding:4px 0;gap:10px;margin-bottom:4px"><span style="width:100px">Região</span><span style="width:44px;text-align:center">Inicial</span><span style="flex:1;text-align:center">Evolução</span><span style="width:44px;text-align:center">Atual</span><span style="width:44px;text-align:right">Delta</span></div>' +
    medidasHTML + '</div>' : '') +
    (sessoesHTML ? '<div class="rel-section"><div class="rel-section-title">Sessões Realizadas</div>' + sessoesHTML + '</div>' : '') +
    '<div class="rel-section"><div class="rel-section-title">Avaliação de Resultados</div>' + avalHTML + '</div>' +
    '</div>' +
    '<div class="rel-footer"><div class="rel-footer-brand">Intelectus · Gestão Inteligente</div><div class="rel-footer-tag">Gerado em ' + dataGerado + '</div></div>' +
    '</div>';

  document.getElementById('ov-relatorio').classList.add('open');
}

// ══════════════════════════════════════════
// FUNCIONALIDADE 3: COMPARATIVO DE PARÂMETROS
// ══════════════════════════════════════════
function renderComparativoInit() {
  var sessoes = _cachedData.sessoes || [];
  var sel = document.getElementById('comp-trat-sel');
  var grupos = {};
  sessoes.forEach(function(s) { if (!grupos[s.trat]) grupos[s.trat] = []; grupos[s.trat].push(s); });
  sel.innerHTML = '<option value="">Selecione o tratamento</option>';
  Object.keys(grupos).filter(function(t){return grupos[t].length>1;}).forEach(function(t) {
    sel.innerHTML += '<option value="' + t + '">' + t + ' (' + grupos[t].length + ' sessões)</option>';
  });
  if (!Object.keys(grupos).length) {
    document.getElementById('comp-content').innerHTML = '<div style="text-align:center;padding:40px;color:var(--silver)"><div style="font-size:2rem;margin-bottom:8px">📊</div><div style="font-size:.78rem">Nenhuma sessão registrada ainda.</div></div>';
  }
}

function renderComparativo(trat) {
  if (!trat) return;
  var sessoes = (_cachedData.sessoes || []).filter(function(s){return s.trat===trat;});
  sessoes.sort(function(a,b){return a.data.localeCompare(b.data)||a.num-b.num;});
  var params = TRAT_DEFS[trat] || [];
  if (!params.length || sessoes.length < 2) {
    document.getElementById('comp-content').innerHTML = '<div style="text-align:center;padding:30px;color:var(--silver);font-size:.78rem">Precisa de pelo menos 2 sessões para comparar.</div>';
    return;
  }
  var cor = TRAT_CORES[trat] || '#c9a84c';
  var html = '<div style="margin-bottom:12px;display:flex;align-items:center;gap:8px">' +
    '<span style="width:10px;height:10px;border-radius:50%;background:' + cor + ';display:inline-block"></span>' +
    '<span style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white)">' + trat + '</span>' +
    '<span style="font-size:.6rem;color:var(--silver)">— ' + sessoes.length + ' sessões registradas</span>' +
    '</div>';
  html += '<div class="comp-wrap"><table class="comp-table"><thead><tr><th>Parâmetro</th>';
  sessoes.forEach(function(s) {
    var dt = s.data ? new Date(s.data+'T12:00:00').toLocaleDateString('pt-BR',{day:'2-digit',month:'2-digit'}) : '';
    html += '<th>Sessão ' + s.num + '<br><span style="font-weight:400;opacity:.6">' + dt + '</span></th>';
  });
  html += '</tr></thead><tbody>';
  params.forEach(function(p) {
    html += '<tr><td class="comp-param">' + p.l + (p.u ? ' <span style="opacity:.5">(' + p.u + ')</span>' : '') + '</td>';
    var vals = sessoes.map(function(s){return s.params ? (s.params[p.l]||'') : '';});
    vals.forEach(function(v, i) {
      var changed = i > 0 && v && v !== vals[0] && vals[0];
      html += '<td class="comp-val' + (changed?' changed':'') + '">' + (v||'<span style="opacity:.3">—</span>') + '</td>';
    });
    html += '</tr>';
  });
  // Resultado + reação
  html += '<tr><td class="comp-param">Resultado</td>';
  sessoes.forEach(function(s) { html += '<td class="comp-val">' + (s.res ? '★'.repeat(parseInt(s.res)) : '—') + '</td>'; });
  html += '</tr><tr><td class="comp-param">Reação</td>';
  sessoes.forEach(function(s) { html += '<td style="font-size:.68rem;color:var(--silver)">' + (s.reac||'—') + '</td>'; });
  html += '</tr></tbody></table></div>';
  // Obs das sessões
  var temObs = sessoes.some(function(s){return s.obs;});
  if (temObs) {
    html += '<div style="margin-top:14px"><div style="font-size:.55rem;letter-spacing:2px;color:var(--gold);text-transform:uppercase;font-weight:700;margin-bottom:8px">Observações por Sessão</div>';
    sessoes.filter(function(s){return s.obs;}).forEach(function(s) {
      var dt = s.data ? new Date(s.data+'T12:00:00').toLocaleDateString('pt-BR') : '';
      html += '<div style="background:var(--n4);border:1px solid var(--bd);border-radius:8px;padding:10px 13px;margin-bottom:7px"><div style="font-size:.6rem;color:var(--gold);font-weight:700;margin-bottom:4px">Sessão ' + s.num + ' · ' + dt + '</div><div style="font-size:.74rem;color:var(--silver);line-height:1.5">' + s.obs + '</div></div>';
    });
    html += '</div>';
  }
  document.getElementById('comp-content').innerHTML = html;
}

// ══════════════════════════════════════════
// FUNCIONALIDADE 4: SCORE POR PROTOCOLO
// ══════════════════════════════════════════
function renderScore() {
  var sessoes = _cachedData.sessoes || [];
  var sc = scores || [0,0,0,0];
  if (!sessoes.length) {
    document.getElementById('score-kpis').innerHTML = '';
    document.getElementById('score-grid').innerHTML = '<div style="text-align:center;padding:40px;color:var(--silver);grid-column:1/-1"><div style="font-size:2rem;margin-bottom:8px">🏆</div><div style="font-family:Cormorant Garamond,serif;font-size:1.1rem;color:var(--white);margin-bottom:4px">Nenhuma sessão registrada</div><div style="font-size:.72rem">Registre sessões para ver o score de cada protocolo</div></div>';
    return;
  }
  // Contar sessões e calcular scores por protocolo
  var protScores = {};
  PROTS.forEach(function(p) {
    var tratNames = p.etapas.map(function(e){return e.trat;});
    var sessoesProt = sessoes.filter(function(s) {
      return tratNames.some(function(t){return s.trat.indexOf(t.split('/')[0].trim())>=0||t.indexOf(s.trat.split('(')[0].trim())>=0;});
    });
    if (!sessoesProt.length) return;
    var resultados = sessoesProt.filter(function(s){return s.res;}).map(function(s){return parseInt(s.res);});
    var avgRes = resultados.length ? resultados.reduce(function(a,v){return a+v;},0)/resultados.length : 0;
    var cobertura = Math.min(sessoesProt.length / 6 * 100, 100);
    var scoreFinal = Math.round((avgRes/5*60) + (cobertura*0.3) + (sc[3]/5*10));
    protScores[p.id] = {prot:p, sessoes:sessoesProt.length, avgRes:avgRes, cobertura:cobertura, score:scoreFinal};
  });
  if (!Object.keys(protScores).length) {
    document.getElementById('score-grid').innerHTML = '<div style="text-align:center;padding:30px;color:var(--silver);grid-column:1/-1;font-size:.78rem">Nenhum protocolo com sessões suficientes ainda.</div>';
    return;
  }
  // KPIs globais
  var scores2 = Object.values(protScores);
  var melhor = scores2.sort(function(a,b){return b.score-a.score;})[0];
  var totalSessScore = sessoes.length;
  var avgGeral = (sc[0]+sc[1]+sc[2]+sc[3])/4;
  document.getElementById('score-kpis').innerHTML =
    '<div class="kpi"><div class="kpi-i">🏆</div><div class="kpi-v">' + (melhor?melhor.prot.name:'--') + '</div><div class="kpi-l">Protocolo top</div></div>' +
    '<div class="kpi"><div class="kpi-i">⭐</div><div class="kpi-v">' + avgGeral.toFixed(1) + '</div><div class="kpi-u">/5</div><div class="kpi-l">Avaliação geral</div></div>' +
    '<div class="kpi"><div class="kpi-i">💉</div><div class="kpi-v">' + totalSessScore + '</div><div class="kpi-l">Sessões totais</div></div>' +
    '<div class="kpi"><div class="kpi-i">📊</div><div class="kpi-v">' + Object.keys(protScores).length + '</div><div class="kpi-l">Protocolos ativos</div></div>';
  var html = '';
  Object.values(protScores).sort(function(a,b){return b.score-a.score;}).forEach(function(ps, rank) {
    var p = ps.prot;
    var medals = ['🥇','🥈','🥉'];
    var medal = medals[rank] || '';
    html += '<div class="score-card">' +
      '<div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:8px">' +
      '<div class="score-name">' + medal + ' ' + p.name + '</div>' +
      '<div style="background:linear-gradient(135deg,var(--gold),#9a6f22);color:var(--ink);font-size:.65rem;font-weight:700;padding:3px 10px;border-radius:10px">' + ps.score + ' pts</div>' +
      '</div>' +
      '<div class="score-bar-row"><div class="score-bar-lbl">Resultado médio</div><div class="score-bar-bg"><div class="score-bar-fill" style="width:' + Math.round(ps.avgRes/5*100) + '%"></div></div><div class="score-val">' + ps.avgRes.toFixed(1) + '/5</div></div>' +
      '<div class="score-bar-row"><div class="score-bar-lbl">Cobertura</div><div class="score-bar-bg"><div class="score-bar-fill" style="width:' + Math.round(ps.cobertura) + '%;background:linear-gradient(to right,#2dd4bf,#80cbc4)"></div></div><div class="score-val">' + Math.round(ps.cobertura) + '%</div></div>' +
      '<div class="score-bar-row"><div class="score-bar-lbl">Satisfação</div><div class="score-bar-bg"><div class="score-bar-fill" style="width:' + Math.round(sc[3]/5*100) + '%;background:linear-gradient(to right,#ce93d8,#f48fb1)"></div></div><div class="score-val">' + sc[3] + '/5</div></div>' +
      '<div class="score-n">' + ps.sessoes + ' sessão(ões) registrada(s)</div>' +
      '</div>';
  });
  document.getElementById('score-grid').innerHTML = html;
}

// =============================================
// MODAL / TOAST
// =============================================
function fechaModal(id) { document.getElementById(id).classList.remove('open'); }
function toast(msg, tipo) {
  var t = document.getElementById('toast');
  t.textContent = msg; t.className = 'toast' + (tipo === 'err' ? ' err' : '');
  t.classList.add('show');
  setTimeout(function() { t.classList.remove('show'); }, 3000);
}

// =============================================

// ══════════════════════════════════════════
// AUTENTICAÇÃO
// ══════════════════════════════════════════
function iniciarAuth() {
  _auth.onAuthStateChanged(function(user) {
    if (user) {
      document.getElementById('tela-login').classList.remove('show');
      document.getElementById('btn-logout').style.display = 'inline-block';
      document.getElementById('user-email').style.display = 'inline';
      document.getElementById('user-email').textContent = user.email;
      mostrarLista();
    } else {
      document.getElementById('tela-login').classList.add('show');
      document.getElementById('btn-logout').style.display = 'none';
      document.getElementById('user-email').style.display = 'none';
      document.getElementById('tela-lista').style.display = 'none';
      document.getElementById('tela-ficha').style.display = 'none';
    }
  });
}

function fazerLogin() {
  var email = document.getElementById('login-email').value.trim();
  var senha = document.getElementById('login-senha').value;
  var btn = document.getElementById('login-btn');
  var err = document.getElementById('login-err');
  err.classList.remove('show');
  if (!email || !senha) { err.textContent = 'Preencha e-mail e senha.'; err.classList.add('show'); return; }
  btn.disabled = true; btn.textContent = 'Entrando...';
  _auth.signInWithEmailAndPassword(email, senha)
    .then(function() { btn.disabled = false; btn.textContent = 'Entrar'; })
    .catch(function(e) {
      btn.disabled = false; btn.textContent = 'Entrar';
      var msgs = {
        'auth/user-not-found':'E-mail nao cadastrado.',
        'auth/wrong-password':'Senha incorreta.',
        'auth/invalid-email':'E-mail invalido.',
        'auth/too-many-requests':'Muitas tentativas. Tente mais tarde.',
        'auth/invalid-credential':'E-mail ou senha incorretos.'
      };
      err.textContent = msgs[e.code] || 'Erro ao entrar. Tente novamente.';
      err.classList.add('show');
    });
}

function loginGoogle() {
  var provider = new firebase.auth.GoogleAuthProvider();
  _auth.signInWithPopup(provider).catch(function(e) {
    var err = document.getElementById('login-err');
    err.textContent = 'Erro ao entrar com Google. Tente novamente.';
    err.classList.add('show');
  });
}

function fazerLogout() {
  if (!confirm('Deseja sair do sistema?')) return;
  _auth.signOut().then(function() { pacKey = null; _cachedData = {}; });
}

function resetSenha() {
  var email = document.getElementById('login-email').value.trim();
  var err = document.getElementById('login-err');
  if (!email) { err.textContent = 'Digite seu e-mail acima para recuperar.'; err.classList.add('show'); return; }
  _auth.sendPasswordResetEmail(email)
    .then(function() {
      err.style.cssText = 'background:rgba(76,186,133,.12);border-color:rgba(76,186,133,.3);color:#4cba85;display:block';
      err.textContent = 'E-mail de recuperacao enviado! Verifique sua caixa de entrada.';
    })
    .catch(function() { err.textContent = 'Erro ao enviar e-mail. Verifique o endereco.'; err.classList.add('show'); });
}

document.addEventListener('keydown', function(e) {
  if (e.key === 'Enter' && document.getElementById('tela-login') && document.getElementById('tela-login').classList.contains('show')) {
    fazerLogin();
  }
});

// INIT — carrega Firebase sequencial depois inicia
// =============================================
renderMed();
renderFotos();
preencherProcsAgenda();
loadScript(
  'https://www.gstatic.com/firebasejs/9.22.0/firebase-app-compat.js',
  function() {
    loadScript(
      'https://www.gstatic.com/firebasejs/9.22.0/firebase-database-compat.js',
      function() {
        loadScript(
          'https://www.gstatic.com/firebasejs/9.22.0/firebase-auth-compat.js',
          function() {
            initFirebase();
            iniciarAuth();
          }
        );
      }
    );
  }
);
</script>
</body>
</html># Cl-nica-
